# LogQA-dataset

Loghub maintains a collection of question answering dataset on three public log datasets: HDFS dataset, OpenSSH dataset and Spark dataset. We select 2,000 logs per dataset as our raw log set. Then we use a question generation model (https://huggingface.co/iarfmoose/t5-base-question-generator) to generate reading comprehension-style questions with answers extracted from a log.

We collected more than 10,000 questions per dataset and then labeled all questions manually and  keep only 2-3% of the data after human annotation.

This is an example of a JSON object that contains QA data. The `Question` field represents the question that was asked about the system, the `Answer` field contains the system's answer, and the `RawLog` field contains the raw log message that the system generated in response to the question.
```
{"Question": "What is the status of the block blk_-6369730481066968769?", "Answer": "terminating", "RawLog": "PacketResponder 1 for block blk_-6369730481066968769 terminating"}
```

The raw log data is listed in HDFS_2k.log_structured.csv/OpenSSH_2k.log_structured.csv/Spark_2k.log_structured.csv, respectively. And we also split the data into training, validation and testing.
