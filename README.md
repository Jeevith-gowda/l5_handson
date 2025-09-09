# Hadoop MapReduce WordCount Project

## 📌 Project Overview
This project demonstrates the **Hadoop MapReduce WordCount** program.  
The goal is to read an input text file, process it using a Mapper and Reducer, and produce the frequency of each word as output.

---

## ⚙️ Approach and Implementation
- **Mapper**:  
  The Mapper reads each line of the input file, splits it into words, and emits each word as a key with a value of `1`.  
  Example:  

Input: "hello world"
Mapper Output: (hello, 1), (world, 1)

- **Reducer**:  
The Reducer takes all values for the same word and sums them up.  
Example:  

Input: (hello, [1, 1])
Reducer Output: (hello, 2)

Together, the program counts the occurrences of every word in the input dataset.

---

## 🚀 Execution Steps
Below are the main commands used:

```bash
# 1. Package the Java project
mvn clean package

# 2. Run Docker containers for Hadoop
docker compose up -d

# 3. Copy input data into HDFS
hdfs dfs -put shared-folder/input/data/input.txt /input

# 4. Run the WordCount job
hadoop jar target/WordCountUsingHadoop-0.0.1-SNAPSHOT.jar com.example.WordCount /input /output

# 5. Retrieve the results
hdfs dfs -cat /output/part-r-00000```



## Challenges faced 
Challenge: Docker Compose not working initially (no configuration file provided).
Solution: Created the docker-compose.yml file properly and ran the command from the correct directory.

Challenge: GitHub push failed due to conflicts with remote repo.
Solution: Uploaded files directly to GitHub to avoid merge conflicts.



## Input given
hello world
how are you doing
good morning
have a good day
good evening
how was your day

## Output

good    3
how     2
your    2
day     2
world   1
own     1
was     1
hello   1
Create  1
morning 1
dataset 1
are     1
evening 1
have    1
input   1
doing   1
you     1
