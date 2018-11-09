Install sbt https://www.scala-sbt.org/0.13/docs/Setup.html

* version 0.13.xx

to download data:
`sbt download`

interactive scala console:
`sbt console`

start spark context:
`val spark = org.apache.spark.sql.SparkSession.builder.master("local[*]").appName("main").getOrCreate()`
`import spark.implicits._`

make table:
`val airTraffic = "airtraffic"`
`val airTrafficTable = spark.read.option("header","true").option("inferSchema", "true").option("nullValue", "NA").csv("LOCATION/src/main/resources/2008.csv ");airTrafficTable.createOrReplaceTempView(airTraffic)`

stop spark:
`spark.stop()`
