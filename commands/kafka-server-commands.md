# Kafka Server Commands

> **All commands should be run from the root of the Kafka installation directory.**

---

## Cleaning Logs After Abrupt Shutdown

1. **Delete** the `tmp` directory created in the root of the working drive.
2. **Format and recreate storage:**
   ```cmd
   .\bin\windows\kafka-storage.bat format --standalone -t kafkastore -c .\config\server.properties
   ```
3. **Start the server** (see below for command).

---

## Navigating to Kafka Installation Directory

```cmd
E:
cd E:\Softwares\kafka_2.13-4.1.0
```

---

## Starting and Stopping the Kafka Server

- **Start server:**
  ```cmd
  .\bin\windows\kafka-server-start.bat .\config\server.properties
  ```
- **Stop server:**
  - Press `Ctrl + C` in the terminal, **or**
  - Run:
    ```cmd
    .\bin\windows\kafka-server-stop.bat
    ```

---

## Topic Management

- **Create a topic:**
  ```cmd
  .\bin\windows\kafka-topics.bat --create --topic quickstart-events --bootstrap-server localhost:9092
  ```
- **Describe a topic:**
  ```cmd
  .\bin\windows\kafka-topics.bat --describe --topic quickstart-events --bootstrap-server localhost:9092
  ```

---

## Producer

- **Start producer:**
  ```cmd
  .\bin\windows\kafka-console-producer.bat --topic quickstart-events --bootstrap-server localhost:9092
  ```

---

## Consumer

- **Start consumer:**
  ```cmd
  .\bin\windows\kafka-console-consumer.bat --topic quickstart-events --from-beginning --bootstrap-server localhost:9092
  ```
