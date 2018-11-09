Install sbt https://www.scala-sbt.org/0.13/docs/Setup.html

* version 0.13.xx

to download data:
`sbt download`

interactive scala console:
`stb consone`

start spark context:
`val spark = org.apache.spark.sql.SparkSession.builder.master("local[*]").appName("main").getOrCreate()`

make table:
`val airTraffic = "airtraffic"`
`val airtrafficTable = spark.read.option("header","true").option("inferSchema", "true").option("nullValue", "NA").csv("/Users/cathy/Desktop/Big-Data-Platforms/a2/dataframe/src/main/resources/2008.csv");airtrafficTable.createOrReplaceTempView(airTraffic)`

stop spark:
`spark.stop()`
