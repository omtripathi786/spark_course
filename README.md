
# Spark Course

this project is my local to learn pysaprk

## Project Structure
```bash
spark_course/
│
├── basic/
│   ├── ratings-counter.py     # PySpark script for generating ratings histogram
│
├── data/
│   ├── ml-100k/               # Folder containing the MovieLens dataset
│   │   ├── u.data             # Input data file for the script
│   │   ├── u.genre
│   │   ├── u.info
│   │   ├── u.item
│   │   ├── ...
```

## Setup Instructions

### 1. Install Java
Apache Spark requires Java to run. Ensure that Java 8, 11, or 17 is installed on your system.
You can download it from [here](https://www.oracle.com/java/technologies/javase-downloads.html).

Check if Java is installed and confirm the version:
```bash
java -version
```

### 2. Install Apache Spark
1. Download a pre-built version of Apache Spark from the [official Spark downloads page](https://spark.apache.org/downloads.html).
2. Extract the downloaded `.tgz` file and move its contents to `C:\spark`.
3. Configure the `log4j2.properties` file to reduce log verbosity:
   - Navigate to `C:\spark\conf`.
   - Rename `log4j2.properties.template` to `log4j2.properties`.
   - Open the file and change the log level from `info` to `error` for less verbose logging.

### 3. Set Environment Variables
Open **Control Panel** → **System and Security** → **System** → **Advanced System Settings** → **Environment Variables** and set the following user variables:
- `SPARK_HOME = C:\spark`
- `PYSPARK_PYTHON = C:\Users\om.tripathi\Anaconda3\envs\py310\python.exe`

Add the following to the **Path** user variable:
- `%SPARK_HOME%\bin`

### 4. Install PySpark
Activate your Python virtual environment and install PySpark:

```bash
conda activate py310
pip install pyspark
```

### 5. Running the Script
You can run the `ratings-counter.py` script either through the terminal using `spark-submit` or directly within PyCharm.

#### Running via `spark-submit`:
```bash
spark-submit basic/ratings-counter.py
```

### 6. PyCharm Configuration
- Ensure PyCharm is using the correct Python interpreter (the virtual environment `py310`).
- Set environment variables in PyCharm for proper Spark execution:
  - `SPARK_HOME = C:\Users\om.tripathi\spark`
  - `PYSPARK_PYTHON = C:\Users\om.tripathi\Anaconda3\envs\py310\python.exe`

To do this, go to `Run` → `Edit Configurations` and add the variables in the **Environment Variables** section.

## MovieLens Dataset
The dataset used for this project is the [MovieLens 100k dataset](https://grouplens.org/datasets/movielens/100k/). It contains 100,000 ratings for 1,682 movies by 943 users.

The `u.data` file contains the ratings in the following format:
```
user_id  movie_id  rating  timestamp
```

### Example of Histogram Output:
```
1 6110
2 11370
3 27145
4 34174
5 21201
```

## Project Dependencies
- **Apache Spark 3.x**
- **Java 8, 11, or 17**
- **Python 3.10 (Anaconda environment)**
- **PyCharm IDE (optional)**

## License
This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
