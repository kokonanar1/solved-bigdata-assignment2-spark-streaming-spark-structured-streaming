Download Link: https://assignmentchef.com/product/solved-bigdata-assignment2-spark-streaming-spark-structured-streaming
<br>
It’s been already a few weeks since you started your short-term internship in the Big Data Engineering Department of the start-up OptimiseYourJourney, which will enter the market next year with a clear goal in mind: “<em>leverage Big Data technologies for improving the user experience in transportation”</em>. Your contribution in Assignment 1 has proven the potential OptimiseYourJourney can obtain by using Spark Core and Spark SQL to analyse public transportation datasets as <strong>Dublin Bus GPS sample data from Dublin City Council (Insight Project)</strong>: <a href="https://data.gov.ie/dataset/dublin-bus-gps-sample-data-from-dublin-city-council-insight-project">https://data.gov.ie/dataset/dublin-bus-gps-sample-data-from-dublin-city</a><a href="https://data.gov.ie/dataset/dublin-bus-gps-sample-data-from-dublin-city-council-insight-project">council-insight-project</a>

In the department meeting that has just finished your boss was particularly happy, again.

<ul>

 <li>First, he thinks this very same Dublin Bus dataset provides a great opportunity to explore the potential of Spark Streaming and Spark Structured Streaming in performing real-time data analysis. To do so, he asks you to adapt the exercises of the previous assignment for their application to these new technologies.</li>

 <li>Second, he is curious about the possibilities other Spark libraries, especifially devoted to Graph and Machine Learning algorithms, would offer when applied to this Dublin Bus Dataset. To do so, he asks you to write a short report about it.</li>

 <li>Third, he is curious about other publicly available transportation-related datasets (they can be focused on cars, buses, trains, taxis, bikes, scooters, etc). To do so, he asks you to write a short report about it.</li>

</ul>

<strong><u>DATASET.</u></strong>

Each real-time dataset you will be dealing with contains a number of files &lt;‘f1.csv’, ‘f2.csv’, ‘f3.csv’, fn.csv’&gt; and represents n batches (of 1 file each) arriving over time for their real-time data analysis. The datasets are provided to you in the folder my_dataset of <strong>Canvas =&gt; 5_Assignments =&gt; A02.zip</strong>.

As in Assignment 1, each row of an Assignment 2 dataset file contains the following fields:

<strong><em>Date , Bus_Line , Bus_Line_Pattern , Congestion , Longitude , Latitude , Delay , Vehicle , Closer_Stop , At_Stop</em></strong>

<ul>

 <li><strong>(00) Date</strong></li>

</ul>

◦ A String representing the date of the measurement with format

&lt;%Y-%m-%d %H:%M:%S&gt;

◦ Example: “2013-01-01 13:00:02”  <strong>(01) Bus_Line</strong>

◦ An Integer representing the bus line.

◦ Example: 120

<ul>

 <li><strong>(02) Bus_Line_Pattern</strong></li>

</ul>

◦ A String identifier for the sequence of stops scheduled in the bus line (different buses of the same bus line can follow different sequence of stops in different iterations).

◦ Example: “027B1001” (it can also be empty “”).  <strong>(03) Congestion</strong>

◦ An Integer representing whether the bus is at a traffic jam (No =&gt; 0 / Yes =&gt; 1) .

◦ Example: 0

<ul>

 <li><strong>(04) Longitude</strong></li>

</ul>

◦ A Float representing the longitude position of the bus.

◦ Example: -6.269634  <strong>(05) Latitude</strong>

◦ A Float representing the latitude position of the bus.

◦ Example:  53.360504

<ul>

 <li><strong>(06) Delay</strong></li>

</ul>

◦ An integer representing the delay of the bus with respect to its schedule (measured in seconds). It is a negative value if the bus is ahead of schedule.

◦ Example:  90.  <strong>(07) Vehicle</strong>

◦ An integer identifier for the bus vehicle.

◦ Example:  33304.  <strong>(08) Closer_Stop</strong>

◦ An integer identifier for the closest bus stop.

◦ Example:  7486.

<ul>

 <li><strong>(09) At_Stop_Stop</strong></li>

</ul>

◦ An integer representing whether the bus vehicle is at the bus stop right now (i.e., stopping at it for passengers to hop on / hop off). (No -&gt; 0 and Yes -&gt; 1)

◦ Example:  0.

<strong><u>TASKS / EXERCISES.</u></strong>

The tasks / exercises to be completed as part of the assignment are described in the next pages of this PDF document.

<ul>

 <li>The following exercises are placed in the folder <strong>my_code:</strong>

  <ol>

   <li>py</li>

   <li>py</li>

   <li>py</li>

   <li>py</li>

   <li>py</li>

   <li>py</li>

   <li>py</li>

   <li>py</li>

  </ol></li>

</ul>

◦ <strong>Each exercise is worth 7.5 marks.</strong>

<strong><u>Rules:</u></strong>

◦ On each exercise, your task is to complete the function <strong>my_model</strong> of the Python program. This function is in charge of specifying the Spark Job performing the real-time data analysis.

◦ When programming my_model, you can create and call as many auxiliary functions as you need.

◦ Do not alter any of the other functions provided: get_source_dir_file_names, streaming_simulation, create_ssc and my_main.

◦ Do not alter the parameters passed to the function my_model.

◦ The entire work must be done “within Spark”:

&#x25aa; The function my_model must start with a creation operation textFileStream or readStream. These operations track the arrival of the batch files and load their content to Spark Streaming and Spark Structured Streaming, respectively.

&#x25aa; The function my_model must finish with an action operation pprint or writeStream printing by the screen the result of the Spark Streaming / Spark Structured Streaming job.

&#x25aa; The function my_model must not contain any other action operation other than the pprint or writeStream appearing at the very end of the function.

◦ The folder my_result contains the expected results for each exercise. Each Spark

Job has been run over the “Small Dataset” (e.g., the file “A01_ex1_spark_streaming.txt” presents the expected result for the Spark Streaming Job for exercise 1 when run over the small dataset).

◦ Suggestion: use a file comparisson app (e.g., Kompare in Ubuntu) to compare your solution to the expected one, ensuring you are getting the right solution and with the right format (please disregard the batch time and the order of the items if the exercise does not explicitly ask you to sort them).

<ul>

 <li>The following exercises are placed in the folder <strong>my_reports:</strong></li>

</ul>

<ol start="9">

 <li>A02_report_additional_spark_libraries.odt 10. A02_report_additional_transportation_dataset.odt</li>

</ol>

◦ <strong>Each report is worth 20 marks.</strong>

◦ Each report must contain a maximum of 1,000 words.

<strong><u>RUBRIC.</u></strong>

<strong>Exercises 1-8.</strong>

<ul>

 <li>20% of the marks =&gt; Complete attempt of the exercise (even if it does not lead to the right solution or right format due to small differences).</li>

 <li>40% of the marks =&gt; Right solution and format (following the aforementioned rules) for the “Small Dataset”.</li>

 <li>40% of the marks =&gt; Right solution and format (following the aforementioned rules) for any “Additional Dataset” test case we will generate. The marks will be allocated in a per test basis (i.e., if 4 extra test are tried, each of them will represent 10% of the marks).</li>

</ul>

<strong>Exercise 9.</strong>

<ul>

 <li>25% of the marks =&gt; Originality.</li>

 <li>25% of the marks =&gt; Relevance.  50% of the marks =&gt; Viability.</li>

</ul>

<strong>Exercise 10.</strong>

<ul>

 <li>25% of the marks =&gt; Brief Description and Main Characteristics.</li>

 <li>25% of the marks =&gt; Relevance.</li>

 <li>50% of the marks =&gt; Viability.</li>

</ul>

<strong><u>SUBMISSION DETAILS / SUBMISSION CODE OF CONDUCT.</u></strong>

Submit to Canvas by the 6<sup>th</sup> of December, 11:59pm.

<ul>

 <li>Submissions up to 1 week late will have 10 marks deducted.</li>

 <li>Submissions up to 2 weeks late will have 20 marks deducted.</li>

</ul>

On submitting the assignment you adhere to the following declaration of authorship. If you have any doubt regarding the plagiarism policy discussed at the beginning of the semester do not hesitate in contacting me.

<strong>Declaration of Authorship</strong>

I, ___YOUR NAME___, declare that the work presented in this assignment titled ‘Assignment 2: Spark Streaming, Spark Structured Streaming, Additional Spark Libraries and Additional Transportation Datasets’ is my own. I confirm that:

<ul>

 <li>This work was done wholly by me as part of my Msc. in Artificial Intelligence, my Msc. in Cyber Security or my Msc. in Software Architecture and Design at Cork Institute of Technology.</li>

 <li>Where I have consulted the published work and source code of others, this is always clearly attributed.</li>

 <li>Where I have quoted from the work of others, the source is always given. With the exception of such quotations, this assignment source code and report is entirely my own work.</li>

</ul>

<strong><u>EXERCISE 1. </u></strong>

In Assignment 1, Exercise 1 was originally applied on Spark Core and Spark SQL. Now, in Assignment 2, we adapt the exercise to a real-time context for its application on Spark Streaming and Spark Structured Streaming. A full description of the original Exercise 1 can be found in the PDF description of Assignment 1 (pages 5-8). In the next sections:

<ul>

 <li>We provide the formal definition for the real-time version of the exercise.</li>

</ul>

◦ We include any potential variation w.r.t. the original version of the problem due to limitations in the functionality of Spark Streaming and Spark Structured Streaming.

<ul>

 <li>We provide an example of a real-time dataset and the solution to be computed for it by Spark Streaming and Spark Structured Streaming.</li>

</ul>

<h1>EXERCISE: FORMAL DEFINITION</h1>

<strong>Given a program passing by parameters: </strong>

<ul>

 <li>The bus stop “bus_stop” (e.g., 279)</li>

 <li>The bus line “bus_line” (e.g., 40)</li>

 <li>A list of hours “hours_list” (e.g., [“08”, “09”] for the intervals [8am – 9am) and [9am – 10), resp.) <strong>and a dataset </strong></li>

 <li>Containing several batches/files arriving over time (e.g., &lt; f1.csv, f2.csv, f3.csv, f4.csv &gt; ) <strong>your task is to: </strong></li>

 <li>Compute the <u>batch accumulated</u> average delay of “bus_line” vehicles when stopping at “bus_stop” for each hour of “hours_list” during weekdays (you must discard any measurement taking place on a Saturday or Sunday).</li>

</ul>

The format of the solution computed <u>after each new batch is processed</u> must be:

<ul>

 <li>&lt; (H1, AD1), (H2, AD2), …, (Hn, ADn) &gt; where:</li>

 <li>Hi is one of the items of “hours_list”. E.g., [8am – 9am).</li>

 <li>ADi is the average delay for all “bus_line” vehicles stopping at “bus_stop” within that hour on a weekday.</li>

 <li><u>Spark Streaming: </u></li>

</ul>

◦ &lt; (H1, AD1), (H2, AD2), …, (Hn, ADn) &gt; are also sorted by increasing order of ADi.

<ul>

 <li><u>Spark Structured Streaming: </u></li>

</ul>

◦ &lt; (H1, AD1), (H2, AD2), …, (Hn, ADn) &gt; <u>are not sorted in any particular order</u>.

<h1>EXAMPLE – SMALL DATASET</h1>

The folder “my_dataset/A02_ex1_micro_dataset” contains an example dataset containing 4 batches/ files

<ul>

 <li>&lt; f1.csv, f2.csv, f3.csv, f4.csv &gt;.</li>

</ul>

Given the aforementioned dataset and program parameters

<ul>

 <li>bus_stop = 279</li>

 <li>bus_line = 40</li>

 <li>hours_list = [“08”, “09”] the files of the folder “my_result”:</li>

 <li>txt =&gt; Solution for Spark Streaming</li>

 <li>txt =&gt; Solution for Spark Structured Streaming Once again, please note the <u>batch accumulated</u> average delay:</li>

 <li>Results for Batch 1 contain the average delay for all measurements of &lt; f1.csv &gt;.</li>

 <li>Results for Batch 2 contain the average delay for all measurements of &lt; f1.csv, f2.csv &gt;.</li>

 <li>Results for Batch 3 contain the average delay for all measurements of &lt; f1.csv, f2.csv, f3.csv &gt;.</li>

 <li>Results for Batch 4 contain the average delay for all measurements of &lt; f1.csv, f2.csv, f3.csv, f4.csv &gt;.</li>

</ul>

<strong><u>EXERCISE 2. </u></strong>

In Assignment 1, Exercise 2 was originally applied on Spark Core and Spark SQL. Now, in Assignment 2, we adapt the exercise to a real-time context for its application on Spark Streaming and Spark Structured Streaming. A full description of the original Exercise 2 can be found in the PDF description of Assignment 1 (pages 9-11). In the next sections:

<ul>

 <li>We provide the formal definition for the real-time version of the exercise.</li>

</ul>

◦ We include any potential variation w.r.t. the original version of the problem due to limitations in the functionality of Spark Streaming and Spark Structured Streaming.

<ul>

 <li>We provide an example of a real-time dataset and the solution to be computed for it by Spark Streaming and Spark Structured Streaming.</li>

</ul>

<h1>EXERCISE: FORMAL DEFINITION</h1>

<strong>Given a program passing by parameters: </strong>– The bus vehicle “vehicle_id” (e.g., 33145) <strong>and a dataset </strong>

<ul>

 <li>Containing several batches/files arriving over time (e.g., &lt; f1.csv, f2.csv, f3.csv, f4.csv &gt; ) <strong>your task is to: </strong></li>

 <li><u>Treat each batch individually (independent from the other batches)</u> and compute <u>per individual batch:</u>

  <ul>

   <li><u>Spark Streaming: </u>The day the “vehicle_id” is serving the highest amount of different bus lines, and the sorted IDs of such bus lines =&gt; Exactly the same as in Assignment 1.</li>

   <li><u>Spark Structured Streaming: </u>Per each day (irrespectively of whether it is the day serving the highest amount of bus lines or not), compute the number of bus lines the vehicle_id is serving  and the sorted IDs of such bus lines =&gt; Different from what we did in Assignment 1.</li>

  </ul></li>

</ul>

The format of the solution computed must be:

<ul>

 <li>&lt; (D1, LB1), (D2, LB2), …, (Dn, LBn) &gt; where:</li>

 <li><u>Spark Streaming: </u></li>

</ul>

◦ Di is the day of the month serving maximum amount of bus lines.

◦ LBi is the list of bus lines served in that concrete day Di.

◦ LBi is sorted by increasing order in the bus line IDs.

◦ Note that &lt; (D1, LB1), (D2, LB2), …, (Dn, LBn) &gt; will have as many pairs (Di, LBi) as days the bus vehicle is serving the very same amount of max bus lines.

◦ If &lt; (D1, LB1), (D2, LB2), …, (Dn, LBn) &gt; contains more than one pair (Di, LBi), then the pairs are also sorted by increasing order of Di.

<ul>

 <li><u>Spark Structured Streaming: </u></li>

</ul>

◦<u> The format is actually &lt; (D1, LB1, NB1), (D2, LB2, NB2), …, (Dn, Lbn, NBn) &gt; </u> ◦<u> There is a tuple (Di, LBi, Nbi) per day registering a measurement </u>.

◦<u> NBi is the number of bus lines served in that concrete day Di </u>.

◦ LBi is the list of bus lines served in that concrete day Di.

◦ LBi is sorted by increasing order in the bus line IDs.

◦ If &lt; (D1, LB1, NB1), (D2, LB2, NB2), …, (Dn, Lbn, NBn) &gt; contains more than one tuple, then the pairs <u>are not sorted sorted in any particular order</u>.

<h1>EXAMPLE – SMALL DATASET</h1>

The folder “my_dataset/A02_ex2_micro_dataset” contains an example dataset containing 4 batches/ files

<ul>

 <li>&lt; f1.csv, f2.csv, f3.csv, f4.csv &gt;.</li>

</ul>

Given the aforementioned dataset and program parameters

<ul>

 <li>vehicle_id = 33145</li>

</ul>

the files of the folder “my_result”:

<ul>

 <li>txt =&gt; Solution for Spark Streaming</li>

 <li>txt =&gt; Solution for Spark Structured Streaming Once again, please note <u>each batch is treated individually (independent from the other batches)</u>:</li>

 <li>Results for Batch 1 contain the bus lines of &lt; f1.csv &gt;.</li>

 <li>Results for Batch 2 contain the bus lines of &lt; f2.csv &gt;.</li>

 <li>Results for Batch 3 contain the bus lines of &lt; f3.csv &gt;.</li>

 <li>Results for Batch 4 contain the bus lines of &lt; f4.csv &gt;.</li>

</ul>

<strong><u>EXERCISE 3. </u></strong>

In Assignment 1, Exercise 3 was originally applied on Spark Core and Spark SQL. Now, in Assignment 2, we adapt the exercise to a real-time context for its application on Spark Streaming and Spark Structured Streaming. A full description of the original Exercise 3 can be found in the PDF description of Assignment 1 (pages 12-14). In the next sections:

<ul>

 <li>We provide the formal definition for the real-time version of the exercise.</li>

</ul>

◦ We include any potential variation w.r.t. the original version of the problem due to limitations in the functionality of Spark Streaming and Spark Structured Streaming.

<ul>

 <li>We provide an example of a real-time dataset and the solution to be computed for it by Spark Streaming and Spark Structured Streaming.</li>

</ul>

<h1>EXERCISE: FORMAL DEFINITION</h1>

<strong>Given a program passing by parameters: </strong>– The bar “threshold_percentage” (e.g., 35.0)  <strong>and a dataset </strong>

<ul>

 <li>Containing several batches/files arriving over time (e.g., &lt; f1.csv, f2.csv, f3.csv, f4.csv &gt; ) <strong>your task is to: </strong></li>

 <li><u>Treating each pair of batches individually (i.e., &lt; Batch 1 &gt;, &lt; Batch 1, Batch 2&gt;, &lt; Batch 2, Batch 3&gt;, …, &lt; Batch n-1, Batch n&gt;:</u> Compute the concrete days and hours having a percentage of measurements reporting congestions above “threshold_percentage”.</li>

</ul>

The format of the solution computed must be:

<ul>

 <li>&lt; (D1, H1, P1), (D2, H2, P2), …, (Dn, Hn, Pn) &gt; where:</li>

 <li>Di is the day of the month (e.g., ’11’ for Friday 11th of January).</li>

 <li>Hi is the hour interval of the day (e.g, ’09’ for the interval [9am – 10am).</li>

 <li>Pi is the percentage of congestion measurements (e.g., 40.00).</li>

 <li><u>Spark Streaming: </u></li>

</ul>

◦ &lt; (D1, H1, P1), (D2, H2, P2), …, (Dn, Hn, Pn) &gt; are sorted by decreasing order of Pi.

<ul>

 <li><u>Spark Structured Streaming: </u></li>

</ul>

◦ &lt; (D1, H1, P1), (D2, H2, P2), …, (Dn, Hn, Pn) &gt; <u>are not sorted in any particular order</u>.

<h1>EXAMPLE – SMALL DATASET</h1>

The folder “my_dataset/A02_ex3_micro_dataset” contains an example dataset containing 4 batches/ files

<ul>

 <li>&lt; f1.csv, f2.csv, f3.csv, f4.csv &gt;.</li>

</ul>

Given the aforementioned dataset and program parameters

<ul>

 <li>threshold_percentage = 35.0 the files of the folder “my_result”:</li>

 <li>txt =&gt; Solution for Spark Streaming</li>

 <li>txt =&gt; Solution for Spark Structured Streaming Once again, please note <u>each pair of batches are treated individually</u>:</li>

 <li>Results for Batch 1 contain the bus lines of &lt; f1.csv &gt;.</li>

 <li>Results for Batch 2 contain the bus lines of &lt; f1.csv, f2.csv &gt;.</li>

 <li>Results for Batch 3 contain the bus lines of &lt; f2.csv, f3.csv &gt;.</li>

 <li>Results for Batch 4 contain the bus lines of &lt; f3.csv, f4.csv &gt;.</li>

</ul>

<strong><u>EXERCISE 4. </u></strong>

In Assignment 1, Exercise 4 was originally applied on Spark Core and Spark SQL. Now, in Assignment 2, we adapt the exercise to a real-time context for its application on Spark Streaming and Spark Structured Streaming. A full description of the original Exercise 4 can be found in the PDF description of Assignment 1 (pages 15-19). In the next sections:

<ul>

 <li>We provide the formal definition for the real-time version of the exercise.</li>

</ul>

◦ We include any potential variation w.r.t. the original version of the problem due to limitations in the functionality of Spark Streaming and Spark Structured Streaming.

<ul>

 <li>We provide an example of a real-time dataset and the solution to be computed for it by Spark Streaming and Spark Structured Streaming.</li>

</ul>

<h1>EXERCISE: FORMAL DEFINITION</h1>

<strong>Given a program passing by parameters: </strong>

<ul>

 <li>The current time “current_time” (e.g., “2013-01-10 08:59:59”)</li>

 <li>A bus stop “current_stop” (e.g., 1935)</li>

 <li>The time you allocate to yourself before you start walking again “seconds_horizon” (e.g., 1800 seconds, which is half an hour).</li>

</ul>

<strong>and a dataset </strong>

<ul>

 <li>Containing several batches/files arriving over time (e.g., &lt; f1.csv, f2.csv, f3.csv, f4.csv &gt; ) <strong>your task is to: </strong></li>

 <li><u>Treat each batch individually (independent from the other batches)</u> and compute <u>per individual </u>batch:

  <ul>

   <li><u>Spark Streaming: </u>Compute the first bus stopping at “current_stop” and the list of bus stops it bring us within that time “seconds_horizon” =&gt; Exactly the same as in Assignment 1.</li>

   <li><u>Spark Structured Streaming: </u>Per each “vehicle_id” (irrespectively of whether it is the first one stopping at “current_stop” or not; moreover, irrespectively of whether it stops at “current_stop” or not) compute the time and stops it stops at. =&gt; Different from what we did in Assignment 1.</li>

  </ul></li>

</ul>

The format of the solution computed must be:

<ul>

 <li>&lt; ( V, [ (T1, S1), (T2, S2), …, (Tn, Sn) ] ) &gt; where:</li>

 <li><u>Spark Streaming: </u></li>

</ul>

◦ V is the first bus vehicle stopping at “current_stop” after “current_time”.

◦ [ (T1, S1), (T2, S2), …, (Tn, Sn) ] is the list of other bus stops this bus vehicle stops at before the end of “current_time” + “seconds_horizon”, with Si being a bus stop and Ti the time stopping at it.

◦ The list includes “current_stop” as S1, so as to know its associated value T1 (i.e., the time we hopped on the bus).

<ul>

 <li><u>Spark Structured Streaming: </u></li>

</ul>

◦<u> The format is actually </u>&lt; (V1,T1, S1),  (V1,T2, S2), …, (V1,Tn1, Sn1), (V2,T1, S1), …, (V2,Tn2, Sn2), … , (Vk,Tnk, Snk) &gt;

◦<u> There is a tuple (V1,T1, S1) per “vehicle_id” and bus stop it stops at during the time horizon.</u>

◦<u> The measurements of each vehicle (V1,T1, S1),  (V1,T2, S2), …, (V1,Tn1, Sn1) are sorted in increasing order in the time the vehicle_id stops at the bus stops. </u>

<h1>EXAMPLE – SMALL DATASET</h1>

The folder “my_dataset/A02_ex4_micro_dataset” contains an example dataset containing 4 batches/ files

<ul>

 <li>&lt; f1.csv, f2.csv, f3.csv, f4.csv &gt;.</li>

</ul>

Given the aforementioned dataset and program parameters

<ul>

 <li>current_time = “2013-01-10 08:59:59”</li>

 <li>current_stop = 1935</li>

 <li>seconds_horizon = 1800</li>

</ul>

the files of the folder “my_result”:

<ul>

 <li>txt =&gt; Solution for Spark Streaming</li>

 <li>txt =&gt; Solution for Spark Structured Streaming Once again, please note <u>each batch is treated individually (independent from the other batches)</u>:</li>

 <li>Results for Batch 1 contain the bus lines of &lt; f1.csv &gt;.</li>

 <li>Results for Batch 2 contain the bus lines of &lt; f2.csv &gt;.</li>

 <li>Results for Batch 3 contain the bus lines of &lt; f3.csv &gt;.</li>

 <li>Results for Batch 4 contain the bus lines of &lt; f4.csv &gt;.</li>

</ul>

<strong><u>EXERCISE 5. </u></strong>

Besides the Spark libraries covered in this semester &lt; Spark Core, Spark SQL and Spark Real-Time   Libs (Spark Streaming &amp; Spark Structured Streaming) &gt; Spark has also:  A library especifially devoted to Graph algorithms

◦ Spark GraphX (for working with RDDs)

◦ Spark GraphFrames (for working with DataFrames)

<ul>

 <li>A library especifially devoted to Machine Learning algorithms</li>

</ul>

◦ Spark MLlib (for working with RDDs)

◦ Spark ML (for working with DataFrames)

Write a report of up to 1,000 words where you present and discuss:

<ul>

 <li>A novel exercise to be included in the data analysis of the Dublin Bus dataset involving the Spark Graph and/or Machine Learning libraries.</li>

</ul>

There is no need to implement the new exercise, you just need to discuss it in terms of:

<ul>

 <li>Its originality – It has to be different from the 4 exercises proposed in Assignments 1 and 2.</li>

 <li>Its relevance – Include a potential use-case derived from the exercise you are proposing.</li>

 <li>Its viability:</li>

</ul>

◦ Do not implement the exercise, but briefly discuss in natural language (English and/or psudocode) the main steps that would be needed so as to implement it.

◦ Include in the discussion whether, if you had to implement it, you would choose to implement it using the library version for working with RDDs or DataFrames. Justify your selection.

◦ Position the new exercise in terms of difficulty with respect to the other four exercises proposed in this assignment.

<strong><u>EXERCISE 6. </u></strong>

Both Assignment 1 and Assignment 2 have had as reference the public transportation dataset

<strong>Dublin Bus GPS sample data from Dublin City Council (Insight Project)</strong>:

<a href="https://data.gov.ie/dataset/dublin-bus-gps-sample-data-from-dublin-city-council-insight-project">https://data.gov.ie/dataset/dublin-bus-gps-sample-data-from-dublin-city-council-insight-project</a>

However, there are many other publicly available transportation-related datasets out there (they can be focused on cars, buses, trains, taxis, bikes, scooters, etc).

Write a report of up to 1,000 words where you present and discuss:

<ul>

 <li>A publicly available transportation-related dataset (different from the Dublin Bus dataset).</li>

</ul>

Compare and contrast the new dataset w.r.t. the Dublin Bus dataset, including:

<ul>

 <li>A brief description of the dataset.</li>

 <li>Its main characteristics: URL for accessing to it, size, format of the data, etc.</li>

 <li>Its relevance – Include a potential use-case derived from the dataset you are proposing that cannot be achieved with the Dublin Bus Dataset.</li>

 <li>Its viability:</li>

</ul>

◦ Do not implement the use-case, but briefly discuss in natural language (English and/or psudocode) the main steps that would be needed so as to implement it.

◦ Include in the discussion the Spark libraries you will use in case you have had to implement it. Justify your selection.

◦ Position the new use-case in terms of difficulty with respect to the other exercises proposed in Assignment 1 and Assignment 2.