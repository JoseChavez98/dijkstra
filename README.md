# dijkstra

ERROR:
21/06/25 00:30:46 INFO mapreduce.Job: Task Id : attempt_1624317487352_0049_r_000004_0, Status : FAILED
Error: java.lang.RuntimeException: PipeMapRed.waitOutputThreads(): subprocess failed with code 1
	at org.apache.hadoop.streaming.PipeMapRed.waitOutputThreads(PipeMapRed.java:325)
	at org.apache.hadoop.streaming.PipeMapRed.mapRedFinished(PipeMapRed.java:538)
	at org.apache.hadoop.streaming.PipeReducer.close(PipeReducer.java:134)
	at org.apache.hadoop.mapred.ReduceTask.runOldReducer(ReduceTask.java:453)
	at org.apache.hadoop.mapred.ReduceTask.run(ReduceTask.java:392)
	at org.apache.hadoop.mapred.YarnChild$2.run(YarnChild.java:177)
	at java.security.AccessController.doPrivileged(Native Method)
	at javax.security.auth.Subject.doAs(Subject.java:422)
	at org.apache.hadoop.security.UserGroupInformation.doAs(UserGroupInformation.java:1926)
	at org.apache.hadoop.mapred.YarnChild.main(YarnChild.java:171)

se le pasa como input el input.dat, tambien intente con input.txt igual se rompe, asi que no es el formato. Le comparto el comando que utilizamos para correrlo

* hadoop jar /usr/lib/hadoop-mapreduce/hadoop-streaming-2.10.1.jar   -file /home/ginger.melo.jc/dijkstra/mapper.py -mapper /home/ginger.melo.jc/dijkstra/mapper.py  -file /home/ginger.melo.jc/dijkstra/reducer.py -reducer  /home/ginger.melo.jc/dijkstra/reducer.py -input data/input.dat -output output

Subiremos el documento a canvas con los detalles del algoritmo, como le mostramos en clase la logica y local funcionan al 100%. Tambien creamos el script para correrlo varias veces y tenemos el script para generar hasta 1M de puntos
