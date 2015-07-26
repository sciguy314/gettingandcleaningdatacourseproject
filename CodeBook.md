#  Getting and Cleaning Data Course Project
##  CodeBook.md

## Data

The following description of the orginal data is taken from the README.txt file that accompanied the original data:

 
> Human Activity Recognition Using Smartphones Dataset  
> Version 1.0  
>  
> Jorge L. Reyes-Ortiz, Davide Anguita, Alessandro Ghio, Luca Oneto.
> Smartlab - Non Linear Complex Systems Laboratory
> DITEN - Universit‡ degli Studi di Genova.
> Via Opera Pia 11A, I-16145, Genoa, Italy.
> activityrecognition@smartlab.ws
> www.smartlab.ws  
> 
> The experiments have been carried out with a group of 30 volunteers within an age bracket > of 19-48 years. Each person performed six activities (WALKING, WALKING_UPSTAIRS, WALKING_DOWNSTAIRS, SITTING, STANDING, LAYING) wearing a smartphone (Samsung Galaxy S II) on the waist. Using its embedded accelerometer and gyroscope, we captured 3-axial linear acceleration and 3-axial angular velocity at a constant rate of 50Hz. The experiments have been video-recorded to label the data manually. The obtained dataset has been randomly partitioned into two sets, where 70% of the volunteers was selected for generating the training data and 30% the test data. 
> 
> The sensor signals (accelerometer and gyroscope) were pre-processed by applying noise filters and then sampled in fixed-width sliding windows of 2.56 sec and 50% overlap (128 readings/window). The sensor acceleration signal, which has gravitational and body motion components, was separated using a Butterworth low-pass filter into body acceleration and gravity. The gravitational force is assumed to have only low frequency components, therefore a filter with 0.3 Hz cutoff frequency was used. From each window, a vector of features was obtained by calculating variables from the time and frequency domain. See 'features_info.txt' for more details. 
> 
> For each record it is provided:  
>
> - Triaxial acceleration from the accelerometer (total acceleration) and the estimated body acceleration.
> - Triaxial Angular velocity from the gyroscope. 
> - A 561-feature vector with time and frequency domain variables. 
> - Its activity label. 
> - An identifier of the subject who carried out the experiment.
> 
> The dataset includes the following files:  
>
> - 'README.txt'
> 
> - 'features_info.txt': Shows information about the variables used on the feature vector.
> 
> - 'features.txt': List of all features.
> 
> - 'activity_labels.txt': Links the class labels with their activity name.
> 
> - 'train/X_train.txt': Training set.
> 
> - 'train/y_train.txt': Training labels.
> 
> - 'test/X_test.txt': Test set.
> 
> - 'test/y_test.txt': Test labels.
> 
> The following files are available for the train and test data. Their descriptions are equivalent. 
> 
> - 'train/subject_train.txt': Each row identifies the subject who performed the activity for each window sample. Its range is from 1 to 30. 

### NOTE: Since the data was normalized it has no units!

## Variables

### Original Data

The following comes from the features.txt document distributed with the original data and describes how the data was collected and labeled in the data set.

>Feature Selection 
>
>The features selected for this database come from the accelerometer and gyroscope 3-axial raw signals tAcc-XYZ and tGyro-XYZ. These time domain signals (prefix 't' to denote time) were captured at a constant rate of 50 Hz. Then they were filtered using a median filter and a 3rd order low pass Butterworth filter with a corner frequency of 20 Hz to remove noise. Similarly, the acceleration signal was then separated into body and gravity acceleration signals (tBodyAcc-XYZ and tGravityAcc-XYZ) using another low pass Butterworth filter with a corner frequency of 0.3 Hz. 
>
>Subsequently, the body linear acceleration and angular velocity were derived in time to obtain Jerk signals (tBodyAccJerk-XYZ and tBodyGyroJerk-XYZ). Also the magnitude of these three-dimensional signals were calculated using the Euclidean norm (tBodyAccMag, tGravityAccMag, tBodyAccJerkMag, tBodyGyroMag, tBodyGyroJerkMag). 
>
>Finally a Fast Fourier Transform (FFT) was applied to some of these signals producing fBodyAcc-XYZ, fBodyAccJerk-XYZ, fBodyGyro-XYZ, fBodyAccJerkMag, fBodyGyroMag, fBodyGyroJerkMag. (Note the 'f' to indicate frequency domain signals). 
>
>These signals were used to estimate variables of the feature vector for each pattern:  
>'-XYZ' is used to denote 3-axial signals in the X, Y and Z directions.
>
>tBodyAcc-XYZ  
>tGravityAcc-XYZ  
>tBodyAccJerk-XYZ  
>tBodyGyro-XYZ  
>tBodyGyroJerk-XYZ  
>tBodyAccMag  
>tGravityAccMag  
>tBodyAccJerkMag  
>tBodyGyroMag  
>tBodyGyroJerkMag  
>fBodyAcc-XYZ  
>fBodyAccJerk-XYZ  
>fBodyGyro-XYZ  
>fBodyAccMag  
>fBodyAccJerkMag  
>fBodyGyroMag  
>fBodyGyroJerkMag  
>
>The set of variables that were estimated from these signals are: 
>
>mean(): Mean value  
>std(): Standard deviation  
>mad(): Median absolute deviation   
>max(): Largest value in array  
>min(): Smallest value in array  
>sma(): Signal magnitude area  
>energy(): Energy measure. Sum of the squares divided by the number of values.
>iqr(): Interquartile range   
>entropy(): Signal entropy  
>arCoeff(): Autorregresion coefficients with Burg order equal to 4  
>correlation(): correlation coefficient between two signals  
>maxInds(): index of the frequency component with largest magnitude  
>meanFreq(): Weighted average of the frequency components to obtain a mean frequency  
>skewness(): skewness of the frequency domain signal   
>kurtosis(): kurtosis of the frequency domain signal   
>bandsEnergy(): Energy of a frequency interval within the 64 bins of the FFT of each window.  
>angle(): Angle between to vectors.  
>
>Additional vectors obtained by averaging the signals in a signal window sample. These are used on the angle() variable:
>
>gravityMean  
>tBodyAccMean  
>tBodyAccJerkMean  
>tBodyGyroMean  
>tBodyGyroJerkMean  
>
>The complete list of variables of each feature vector is available in 'features.txt'


### Column Names in **completeData**

These variable names were edited within run_analysis.R to standardize their appearance. The following changes were made

* "()" were removed
* "-" were replaced with "."

  This resulted in the following variables  
   Column Name              |       Description of Contents  
----------------------------|-------------------------------------  
1 subject                   | Study participant identifier, 1...30  
2 activity                  | Type of activity, factor, 6 levels, see   
3 type                      | "Train" or "Test"  
4 tBodyAcc.mean.X   | Time domain body acceleration mean in X axis  
5 tBodyAcc.mean.Y   | Time domain body acceleration  
6 tBodyAcc.mean.Z   | Time domain body acceleration  
7 tBodyAcc.std.X    | Time domain body acceleration  
8 tBodyAcc.std.Y    | Time domain body acceleration  
9 tBodyAcc.std.Z    | Time domain body acceleration  
10 tBodyAcc.mad.X   | Time domain body acceleration  
11 tBodyAcc.mad.Y   | Time domain body acceleration  
12 tBodyAcc.mad.Z   | Time domain body acceleration  
13 tBodyAcc.max.X   | Time domain body acceleration  
14 tBodyAcc.max.Y   | Time domain body acceleration  
15 tBodyAcc.max.Z   | Time domain body acceleration  
16 tBodyAcc.min.X   | Time domain body acceleration  
17 tBodyAcc.min.Y   | Time domain body acceleration  
18 tBodyAcc.min.Z   | Time domain body acceleration  
19 tBodyAcc.sma | Time domain body acceleration  
20 tBodyAcc.energy.X    | Time domain body acceleration  
21 tBodyAcc.energy.Y    | Time domain body acceleration  
22 tBodyAcc.energy.Z    | Time domain body acceleration  
23 tBodyAcc.iqr.X   | Time domain body acceleration  
24 tBodyAcc.iqr.Y   | Time domain body acceleration  
25 tBodyAcc.iqr.Z   | Time domain body acceleration  
26 tBodyAcc.entropy.X   | Time domain body acceleration  
27 tBodyAcc.entropy.Y   | Time domain body acceleration  
28 tBodyAcc.entropy.Z   | Time domain body acceleration  
29 tBodyAcc.arCoeff.X.1 | Time domain body acceleration  
30 tBodyAcc.arCoeff.X.2 | Time domain body acceleration  
31 tBodyAcc.arCoeff.X.3 | Time domain body acceleration  
32 tBodyAcc.arCoeff.X.4 | Time domain body acceleration  
33 tBodyAcc.arCoeff.Y.1 | Time domain body acceleration  
34 tBodyAcc.arCoeff.Y.2 | Time domain body acceleration  
35 tBodyAcc.arCoeff.Y.3 | Time domain body acceleration  
36 tBodyAcc.arCoeff.Y.4 | Time domain body acceleration  
37 tBodyAcc.arCoeff.Z.1 | Time domain body acceleration  
38 tBodyAcc.arCoeff.Z.2 | Time domain body acceleration  
39 tBodyAcc.arCoeff.Z.3 | Time domain body acceleration  
40 tBodyAcc.arCoeff.Z.4 | Time domain body acceleration  
41 tBodyAcc.correlation.X.Y | Time domain body acceleration  
42 tBodyAcc.correlation.X.Z | Time domain body acceleration  
43 tBodyAcc.correlation.Y.Z | Time domain body acceleration  
44 tGravityAcc.mean.X   | Time domain acceleration due to gravity  
45 tGravityAcc.mean.Y   | Time domain acceleration due to gravity  
46 tGravityAcc.mean.Z   | Time domain acceleration due to gravity  
47 tGravityAcc.std.X    | Time domain acceleration due to gravity  
48 tGravityAcc.std.Y    | Time domain acceleration due to gravity  
49 tGravityAcc.std.Z    | Time domain acceleration due to gravity  
50 tGravityAcc.mad.X    | Time domain acceleration due to gravity  
51 tGravityAcc.mad.Y    | Time domain acceleration due to gravity  
52 tGravityAcc.mad.Z    | Time domain acceleration due to gravity  
53 tGravityAcc.max.X    | Time domain acceleration due to gravity  
54 tGravityAcc.max.Y    | Time domain acceleration due to gravity  
55 tGravityAcc.max.Z    | Time domain acceleration due to gravity  
56 tGravityAcc.min.X    | Time domain acceleration due to gravity  
57 tGravityAcc.min.Y    | Time domain acceleration due to gravity  
58 tGravityAcc.min.Z    | Time domain acceleration due to gravity  
59 tGravityAcc.sma  | Time domain acceleration due to gravity  
60 tGravityAcc.energy.X | Time domain acceleration due to gravity  
61 tGravityAcc.energy.Y | Time domain acceleration due to gravity  
62 tGravityAcc.energy.Z | Time domain acceleration due to gravity  
63 tGravityAcc.iqr.X    | Time domain acceleration due to gravity  
64 tGravityAcc.iqr.Y    | Time domain acceleration due to gravity  
65 tGravityAcc.iqr.Z    | Time domain acceleration due to gravity  
66 tGravityAcc.entropy.X    | Time domain acceleration due to gravity  
67 tGravityAcc.entropy.Y    | Time domain acceleration due to gravity  
68 tGravityAcc.entropy.Z    | Time domain acceleration due to gravity  
69 tGravityAcc.arCoeff.X.1  | Time domain acceleration due to gravity  
70 tGravityAcc.arCoeff.X.2  | Time domain acceleration due to gravity  
71 tGravityAcc.arCoeff.X.3  | Time domain acceleration due to gravity  
72 tGravityAcc.arCoeff.X.4  | Time domain acceleration due to gravity  
73 tGravityAcc.arCoeff.Y.1  | Time domain acceleration due to gravity  
74 tGravityAcc.arCoeff.Y.2  | Time domain acceleration due to gravity  
75 tGravityAcc.arCoeff.Y.3  | Time domain acceleration due to gravity  
76 tGravityAcc.arCoeff.Y.4  | Time domain acceleration due to gravity  
77 tGravityAcc.arCoeff.Z.1  | Time domain acceleration due to gravity  
78 tGravityAcc.arCoeff.Z.2  | Time domain acceleration due to gravity  
79 tGravityAcc.arCoeff.Z.3  | Time domain acceleration due to gravity  
80 tGravityAcc.arCoeff.Z.4  | Time domain acceleration due to gravity  
81 tGravityAcc.correlation.X.Y  | Time domain acceleration due to gravity  
82 tGravityAcc.correlation.X.Z  | Time domain acceleration due to gravity  
83 tGravityAcc.correlation.Y.Z  | Time domain acceleration due to gravity  
84 tBodyAccJerk.mean.X  | Time domain body jerk  
85 tBodyAccJerk.mean.Y  | Time domain body jerk  
86 tBodyAccJerk.mean.Z  | Time domain body jerk  
87 tBodyAccJerk.std.X   | Time domain body jerk  
88 tBodyAccJerk.std.Y   | Time domain body jerk  
89 tBodyAccJerk.std.Z   | Time domain body jerk  
90 tBodyAccJerk.mad.X   | Time domain body jerk  
91 tBodyAccJerk.mad.Y   | Time domain body jerk  
92 tBodyAccJerk.mad.Z   | Time domain body jerk  
93 tBodyAccJerk.max.X   | Time domain body jerk  
94 tBodyAccJerk.max.Y   | Time domain body jerk  
95 tBodyAccJerk.max.Z   | Time domain body jerk  
96 tBodyAccJerk.min.X   | Time domain body jerk  
97 tBodyAccJerk.min.Y   | Time domain body jerk  
98 tBodyAccJerk.min.Z   | Time domain body jerk  
99 tBodyAccJerk.sma | Time domain body jerk  
100 tBodyAccJerk.energy.X   | Time domain body jerk  
101 tBodyAccJerk.energy.Y   | Time domain body jerk  
102 tBodyAccJerk.energy.Z   | Time domain body jerk  
103 tBodyAccJerk.iqr.X  | Time domain body jerk  
104 tBodyAccJerk.iqr.Y  | Time domain body jerk  
105 tBodyAccJerk.iqr.Z  | Time domain body jerk  
106 tBodyAccJerk.entropy.X  | Time domain body jerk  
107 tBodyAccJerk.entropy.Y  | Time domain body jerk  
108 tBodyAccJerk.entropy.Z  | Time domain body jerk  
109 tBodyAccJerk.arCoeff.X.1    | Time domain body jerk  
110 tBodyAccJerk.arCoeff.X.2    | Time domain body jerk  
111 tBodyAccJerk.arCoeff.X.3    | Time domain body jerk  
112 tBodyAccJerk.arCoeff.X.4    | Time domain body jerk  
113 tBodyAccJerk.arCoeff.Y.1    | Time domain body jerk  
114 tBodyAccJerk.arCoeff.Y.2    | Time domain body jerk  
115 tBodyAccJerk.arCoeff.Y.3    | Time domain body jerk  
116 tBodyAccJerk.arCoeff.Y.4    | Time domain body jerk  
117 tBodyAccJerk.arCoeff.Z.1    | Time domain body jerk  
118 tBodyAccJerk.arCoeff.Z.2    | Time domain body jerk  
119 tBodyAccJerk.arCoeff.Z.3    | Time domain body jerk  
120 tBodyAccJerk.arCoeff.Z.4    | Time domain body jerk  
121 tBodyAccJerk.correlation.X.Y    | Time domain body jerk  
122 tBodyAccJerk.correlation.X.Z    | Time domain body jerk  
123 tBodyAccJerk.correlation.Y.Z    | Time domain body jerk  
124 tBodyGyro.mean.X    | Time domain body gyroscopic jerk  
125 tBodyGyro.mean.Y    | Time domain body gyroscopic jerk  
126 tBodyGyro.mean.Z    | Time domain body gyroscopic jerk  
127 tBodyGyro.std.X | Time domain body gyroscopic jerk  
128 tBodyGyro.std.Y | Time domain body gyroscopic jerk  
129 tBodyGyro.std.Z | Time domain body gyroscopic jerk  
130 tBodyGyro.mad.X | Time domain body gyroscopic jerk  
131 tBodyGyro.mad.Y | Time domain body gyroscopic jerk  
132 tBodyGyro.mad.Z | Time domain body gyroscopic jerk  
133 tBodyGyro.max.X | Time domain body gyroscopic jerk  
134 tBodyGyro.max.Y | Time domain body gyroscopic jerk  
135 tBodyGyro.max.Z | Time domain body gyroscopic jerk  
136 tBodyGyro.min.X | Time domain body gyroscopic jerk  
137 tBodyGyro.min.Y | Time domain body gyroscopic jerk  
138 tBodyGyro.min.Z | Time domain body gyroscopic jerk  
139 tBodyGyro.sma   | Time domain body gyroscopic jerk  
140 tBodyGyro.energy.X  | Time domain body gyroscopic jerk  
141 tBodyGyro.energy.Y  | Time domain body gyroscopic jerk  
142 tBodyGyro.energy.Z  | Time domain body gyroscopic jerk  
143 tBodyGyro.iqr.X | Time domain body gyroscopic jerk  
144 tBodyGyro.iqr.Y | Time domain body gyroscopic jerk  
145 tBodyGyro.iqr.Z | Time domain body gyroscopic jerk  
146 tBodyGyro.entropy.X | Time domain body gyroscopic jerk  
147 tBodyGyro.entropy.Y | Time domain body gyroscopic jerk  
148 tBodyGyro.entropy.Z | Time domain body gyroscopic jerk  
149 tBodyGyro.arCoeff.X.1   | Time domain body gyroscopic jerk  
150 tBodyGyro.arCoeff.X.2   | Time domain body gyroscopic jerk  
151 tBodyGyro.arCoeff.X.3   | Time domain body gyroscopic jerk  
152 tBodyGyro.arCoeff.X.4   | Time domain body gyroscopic jerk  
153 tBodyGyro.arCoeff.Y.1   | Time domain body gyroscopic jerk  
154 tBodyGyro.arCoeff.Y.2   | Time domain body gyroscopic jerk  
155 tBodyGyro.arCoeff.Y.3   | Time domain body gyroscopic jerk  
156 tBodyGyro.arCoeff.Y.4   | Time domain body gyroscopic jerk  
157 tBodyGyro.arCoeff.Z.1   | Time domain body gyroscopic jerk  
158 tBodyGyro.arCoeff.Z.2   | Time domain body gyroscopic jerk  
159 tBodyGyro.arCoeff.Z.3   | Time domain body gyroscopic jerk  
160 tBodyGyro.arCoeff.Z.4   | Time domain body gyroscopic jerk  
161 tBodyGyro.correlation.X.Y   | Time domain body gyroscopic jerk  
162 tBodyGyro.correlation.X.Z   | Time domain body gyroscopic jerk  
163 tBodyGyro.correlation.Y.Z   | Time domain body gyroscopic jerk  
164 tBodyGyroJerk.mean.X    | Time domain body gyroscopic jerk  
165 tBodyGyroJerk.mean.Y    | Time domain body gyroscopic jerk  
166 tBodyGyroJerk.mean.Z    | Time domain body gyroscopic jerk  
167 tBodyGyroJerk.std.X | Time domain body gyroscopic jerk  
168 tBodyGyroJerk.std.Y | Time domain body gyroscopic jerk  
169 tBodyGyroJerk.std.Z | Time domain body gyroscopic jerk  
170 tBodyGyroJerk.mad.X | Time domain body gyroscopic jerk  
171 tBodyGyroJerk.mad.Y | Time domain body gyroscopic jerk  
172 tBodyGyroJerk.mad.Z | Time domain body gyroscopic jerk  
173 tBodyGyroJerk.max.X | Time domain body gyroscopic jerk  
174 tBodyGyroJerk.max.Y | Time domain body gyroscopic jerk  
175 tBodyGyroJerk.max.Z | Time domain body gyroscopic jerk  
176 tBodyGyroJerk.min.X | Time domain body gyroscopic jerk  
177 tBodyGyroJerk.min.Y | Time domain body gyroscopic jerk  
178 tBodyGyroJerk.min.Z | Time domain body gyroscopic jerk  
179 tBodyGyroJerk.sma   | Time domain body gyroscopic jerk  
180 tBodyGyroJerk.energy.X  |   
181 tBodyGyroJerk.energy.Y  |   
182 tBodyGyroJerk.energy.Z  |   
183 tBodyGyroJerk.iqr.X |   
184 tBodyGyroJerk.iqr.Y |   
185 tBodyGyroJerk.iqr.Z |   
186 tBodyGyroJerk.entropy.X |   
187 tBodyGyroJerk.entropy.Y |   
188 tBodyGyroJerk.entropy.Z |   
189 tBodyGyroJerk.arCoeff.X.1   |   
190 tBodyGyroJerk.arCoeff.X.2   |   
191 tBodyGyroJerk.arCoeff.X.3   |   
192 tBodyGyroJerk.arCoeff.X.4   |   
193 tBodyGyroJerk.arCoeff.Y.1   |   
194 tBodyGyroJerk.arCoeff.Y.2   |   
195 tBodyGyroJerk.arCoeff.Y.3   |   
196 tBodyGyroJerk.arCoeff.Y.4   |   
197 tBodyGyroJerk.arCoeff.Z.1   |   
198 tBodyGyroJerk.arCoeff.Z.2   |   
199 tBodyGyroJerk.arCoeff.Z.3   |   
200 tBodyGyroJerk.arCoeff.Z.4   |   
201 tBodyGyroJerk.correlation.X.Y   |   
202 tBodyGyroJerk.correlation.X.Z   |   
203 tBodyGyroJerk.correlation.Y.Z   |   
204 tBodyAccMag.mean    |   
205 tBodyAccMag.std |   
206 tBodyAccMag.mad |   
207 tBodyAccMag.max |   
208 tBodyAccMag.min |   
209 tBodyAccMag.sma |   
210 tBodyAccMag.energy  |   
211 tBodyAccMag.iqr |   
212 tBodyAccMag.entropy |   
213 tBodyAccMag.arCoeff1    |   
214 tBodyAccMag.arCoeff2    |   
215 tBodyAccMag.arCoeff3    |   
216 tBodyAccMag.arCoeff4    |   
217 tGravityAccMag.mean |   
218 tGravityAccMag.std  |   
219 tGravityAccMag.mad  |   
220 tGravityAccMag.max  |   
221 tGravityAccMag.min  |   
222 tGravityAccMag.sma  |   
223 tGravityAccMag.energy   |   
224 tGravityAccMag.iqr  |   
225 tGravityAccMag.entropy  |   
226 tGravityAccMag.arCoeff1 |   
227 tGravityAccMag.arCoeff2 |   
228 tGravityAccMag.arCoeff3 |   
229 tGravityAccMag.arCoeff4 |   
230 tBodyAccJerkMag.mean    |   
231 tBodyAccJerkMag.std |   
232 tBodyAccJerkMag.mad |   
233 tBodyAccJerkMag.max |   
234 tBodyAccJerkMag.min |   
235 tBodyAccJerkMag.sma |   
236 tBodyAccJerkMag.energy  |   
237 tBodyAccJerkMag.iqr |   
238 tBodyAccJerkMag.entropy |   
239 tBodyAccJerkMag.arCoeff1    |   
240 tBodyAccJerkMag.arCoeff2    |   
241 tBodyAccJerkMag.arCoeff3    |   
242 tBodyAccJerkMag.arCoeff4    |   
243 tBodyGyroMag.mean   |   
244 tBodyGyroMag.std    |   
245 tBodyGyroMag.mad    |   
246 tBodyGyroMag.max    |   
247 tBodyGyroMag.min    |   
248 tBodyGyroMag.sma    |   
249 tBodyGyroMag.energy |   
250 tBodyGyroMag.iqr    |   
251 tBodyGyroMag.entropy    |   
252 tBodyGyroMag.arCoeff1   |   
253 tBodyGyroMag.arCoeff2   |   
254 tBodyGyroMag.arCoeff3   |   
255 tBodyGyroMag.arCoeff4   |   
256 tBodyGyroJerkMag.mean   |   
257 tBodyGyroJerkMag.std    |   
258 tBodyGyroJerkMag.mad    |   
259 tBodyGyroJerkMag.max    |   
260 tBodyGyroJerkMag.min    |   
261 tBodyGyroJerkMag.sma    |   
262 tBodyGyroJerkMag.energy |   
263 tBodyGyroJerkMag.iqr    |   
264 tBodyGyroJerkMag.entropy    |   
265 tBodyGyroJerkMag.arCoeff1   |   
266 tBodyGyroJerkMag.arCoeff2   |   
267 tBodyGyroJerkMag.arCoeff3   |   
268 tBodyGyroJerkMag.arCoeff4   |   
269 fBodyAcc.mean.X |   
270 fBodyAcc.mean.Y |   
271 fBodyAcc.mean.Z |   
272 fBodyAcc.std.X  |   
273 fBodyAcc.std.Y  |   
274 fBodyAcc.std.Z  |   
275 fBodyAcc.mad.X  |   
276 fBodyAcc.mad.Y  |   
277 fBodyAcc.mad.Z  |   
278 fBodyAcc.max.X  |   
279 fBodyAcc.max.Y  |   
280 fBodyAcc.max.Z  |   
281 fBodyAcc.min.X  |   
282 fBodyAcc.min.Y  |   
283 fBodyAcc.min.Z  |   
284 fBodyAcc.sma    |   
285 fBodyAcc.energy.X   |   
286 fBodyAcc.energy.Y   |   
287 fBodyAcc.energy.Z   |   
288 fBodyAcc.iqr.X  |   
289 fBodyAcc.iqr.Y  |   
290 fBodyAcc.iqr.Z  |   
291 fBodyAcc.entropy.X  |   
292 fBodyAcc.entropy.Y  |   
293 fBodyAcc.entropy.Z  |   
294 fBodyAcc.maxInds.X  |   
295 fBodyAcc.maxInds.Y  |   
296 fBodyAcc.maxInds.Z  |   
297 fBodyAcc.meanFreq.X |   
298 fBodyAcc.meanFreq.Y |   
299 fBodyAcc.meanFreq.Z |   
300 fBodyAcc.skewness.X |   
301 fBodyAcc.kurtosis.X |   
302 fBodyAcc.skewness.Y |   
303 fBodyAcc.kurtosis.Y |   
304 fBodyAcc.skewness.Z |   
305 fBodyAcc.kurtosis.Z |   
306 fBodyAcc.bandsEnergy.1.8    |   
307 fBodyAcc.bandsEnergy.9.16   |   
308 fBodyAcc.bandsEnergy.17.24  |   
309 fBodyAcc.bandsEnergy.25.32  |   
310 fBodyAcc.bandsEnergy.33.40  |   
311 fBodyAcc.bandsEnergy.41.48  |   
312 fBodyAcc.bandsEnergy.49.56  |   
313 fBodyAcc.bandsEnergy.57.64  |   
314 fBodyAcc.bandsEnergy.1.16   |   
315 fBodyAcc.bandsEnergy.17.32  |   
316 fBodyAcc.bandsEnergy.33.48  |   
317 fBodyAcc.bandsEnergy.49.64  |   
318 fBodyAcc.bandsEnergy.1.24   |   
319 fBodyAcc.bandsEnergy.25.48  |   
320 fBodyAcc.bandsEnergy.1.8.1  |   
321 fBodyAcc.bandsEnergy.9.16.1 |   
322 fBodyAcc.bandsEnergy.17.24.1    |   
323 fBodyAcc.bandsEnergy.25.32.1    |   
324 fBodyAcc.bandsEnergy.33.40.1    |   
325 fBodyAcc.bandsEnergy.41.48.1    |   
326 fBodyAcc.bandsEnergy.49.56.1    |   
327 fBodyAcc.bandsEnergy.57.64.1    |   
328 fBodyAcc.bandsEnergy.1.16.1 |   
329 fBodyAcc.bandsEnergy.17.32.1    |   
330 fBodyAcc.bandsEnergy.33.48.1    |   
331 fBodyAcc.bandsEnergy.49.64.1    |   
332 fBodyAcc.bandsEnergy.1.24.1 |   
333 fBodyAcc.bandsEnergy.25.48.1    |   
334 fBodyAcc.bandsEnergy.1.8.2  |   
335 fBodyAcc.bandsEnergy.9.16.2 |   
336 fBodyAcc.bandsEnergy.17.24.2    |   
337 fBodyAcc.bandsEnergy.25.32.2    |   
338 fBodyAcc.bandsEnergy.33.40.2    |   
339 fBodyAcc.bandsEnergy.41.48.2    |   
340 fBodyAcc.bandsEnergy.49.56.2    |   
341 fBodyAcc.bandsEnergy.57.64.2    |   
342 fBodyAcc.bandsEnergy.1.16.2 |   
343 fBodyAcc.bandsEnergy.17.32.2    |   
344 fBodyAcc.bandsEnergy.33.48.2    |   
345 fBodyAcc.bandsEnergy.49.64.2    |   
346 fBodyAcc.bandsEnergy.1.24.2 |   
347 fBodyAcc.bandsEnergy.25.48.2    |   
348 fBodyAccJerk.mean.X |   
349 fBodyAccJerk.mean.Y |   
350 fBodyAccJerk.mean.Z |   
351 fBodyAccJerk.std.X  |   
352 fBodyAccJerk.std.Y  |   
353 fBodyAccJerk.std.Z  |   
354 fBodyAccJerk.mad.X  |   
355 fBodyAccJerk.mad.Y  |   
356 fBodyAccJerk.mad.Z  |   
357 fBodyAccJerk.max.X  |   
358 fBodyAccJerk.max.Y  |   
359 fBodyAccJerk.max.Z  |   
360 fBodyAccJerk.min.X  |   
361 fBodyAccJerk.min.Y  |   
362 fBodyAccJerk.min.Z  |   
363 fBodyAccJerk.sma    |   
364 fBodyAccJerk.energy.X   |   
365 fBodyAccJerk.energy.Y   |   
366 fBodyAccJerk.energy.Z   |   
367 fBodyAccJerk.iqr.X  |   
368 fBodyAccJerk.iqr.Y  |   
369 fBodyAccJerk.iqr.Z  |   
370 fBodyAccJerk.entropy.X  |   
371 fBodyAccJerk.entropy.Y  |   
372 fBodyAccJerk.entropy.Z  |   
373 fBodyAccJerk.maxInds.X  |   
374 fBodyAccJerk.maxInds.Y  |   
375 fBodyAccJerk.maxInds.Z  |   
376 fBodyAccJerk.meanFreq.X |   
377 fBodyAccJerk.meanFreq.Y |   
378 fBodyAccJerk.meanFreq.Z |   
379 fBodyAccJerk.skewness.X |   
380 fBodyAccJerk.kurtosis.X |   
381 fBodyAccJerk.skewness.Y |   
382 fBodyAccJerk.kurtosis.Y |   
383 fBodyAccJerk.skewness.Z |   
384 fBodyAccJerk.kurtosis.Z |   
385 fBodyAccJerk.bandsEnergy.1.8    |   
386 fBodyAccJerk.bandsEnergy.9.16   |   
387 fBodyAccJerk.bandsEnergy.17.24  |   
388 fBodyAccJerk.bandsEnergy.25.32  |   
389 fBodyAccJerk.bandsEnergy.33.40  |   
390 fBodyAccJerk.bandsEnergy.41.48  |   
391 fBodyAccJerk.bandsEnergy.49.56  |   
392 fBodyAccJerk.bandsEnergy.57.64  |   
393 fBodyAccJerk.bandsEnergy.1.16   |   
394 fBodyAccJerk.bandsEnergy.17.32  |   
395 fBodyAccJerk.bandsEnergy.33.48  |   
396 fBodyAccJerk.bandsEnergy.49.64  |   
397 fBodyAccJerk.bandsEnergy.1.24   |   
398 fBodyAccJerk.bandsEnergy.25.48  |   
399 fBodyAccJerk.bandsEnergy.1.8.1  |   
400 fBodyAccJerk.bandsEnergy.9.16.1 |   
401 fBodyAccJerk.bandsEnergy.17.24.1    |   
402 fBodyAccJerk.bandsEnergy.25.32.1    |   
403 fBodyAccJerk.bandsEnergy.33.40.1    |   
404 fBodyAccJerk.bandsEnergy.41.48.1    |   
405 fBodyAccJerk.bandsEnergy.49.56.1    |   
406 fBodyAccJerk.bandsEnergy.57.64.1    |   
407 fBodyAccJerk.bandsEnergy.1.16.1 |   
408 fBodyAccJerk.bandsEnergy.17.32.1    |   
409 fBodyAccJerk.bandsEnergy.33.48.1    |   
410 fBodyAccJerk.bandsEnergy.49.64.1    |   
411 fBodyAccJerk.bandsEnergy.1.24.1 |   
412 fBodyAccJerk.bandsEnergy.25.48.1    |   
413 fBodyAccJerk.bandsEnergy.1.8.2  |   
414 fBodyAccJerk.bandsEnergy.9.16.2 |   
415 fBodyAccJerk.bandsEnergy.17.24.2    |   
416 fBodyAccJerk.bandsEnergy.25.32.2    |   
417 fBodyAccJerk.bandsEnergy.33.40.2    |   
418 fBodyAccJerk.bandsEnergy.41.48.2    |   
419 fBodyAccJerk.bandsEnergy.49.56.2    |   
420 fBodyAccJerk.bandsEnergy.57.64.2    |   
421 fBodyAccJerk.bandsEnergy.1.16.2 |   
422 fBodyAccJerk.bandsEnergy.17.32.2    |   
423 fBodyAccJerk.bandsEnergy.33.48.2    |   
424 fBodyAccJerk.bandsEnergy.49.64.2    |   
425 fBodyAccJerk.bandsEnergy.1.24.2 |   
426 fBodyAccJerk.bandsEnergy.25.48.2    |   
427 fBodyGyro.mean.X    |   
428 fBodyGyro.mean.Y    |   
429 fBodyGyro.mean.Z    |   
430 fBodyGyro.std.X |   
431 fBodyGyro.std.Y |   
432 fBodyGyro.std.Z |   
433 fBodyGyro.mad.X |   
434 fBodyGyro.mad.Y |   
435 fBodyGyro.mad.Z |   
436 fBodyGyro.max.X |   
437 fBodyGyro.max.Y |   
438 fBodyGyro.max.Z |   
439 fBodyGyro.min.X |   
440 fBodyGyro.min.Y |   
441 fBodyGyro.min.Z |   
442 fBodyGyro.sma   |   
443 fBodyGyro.energy.X  |   
444 fBodyGyro.energy.Y  |   
445 fBodyGyro.energy.Z  |   
446 fBodyGyro.iqr.X |   
447 fBodyGyro.iqr.Y |   
448 fBodyGyro.iqr.Z |   
449 fBodyGyro.entropy.X |   
450 fBodyGyro.entropy.Y |   
451 fBodyGyro.entropy.Z |   
452 fBodyGyro.maxInds.X |   
453 fBodyGyro.maxInds.Y |   
454 fBodyGyro.maxInds.Z |   
455 fBodyGyro.meanFreq.X    |   
456 fBodyGyro.meanFreq.Y    |   
457 fBodyGyro.meanFreq.Z    |   
458 fBodyGyro.skewness.X    |   
459 fBodyGyro.kurtosis.X    |   
460 fBodyGyro.skewness.Y    |   
461 fBodyGyro.kurtosis.Y    |   
462 fBodyGyro.skewness.Z    |   
463 fBodyGyro.kurtosis.Z    |   
464 fBodyGyro.bandsEnergy.1.8   |   
465 fBodyGyro.bandsEnergy.9.16  |   
466 fBodyGyro.bandsEnergy.17.24 |   
467 fBodyGyro.bandsEnergy.25.32 |   
468 fBodyGyro.bandsEnergy.33.40 |   
469 fBodyGyro.bandsEnergy.41.48 |   
470 fBodyGyro.bandsEnergy.49.56 |   
471 fBodyGyro.bandsEnergy.57.64 |   
472 fBodyGyro.bandsEnergy.1.16  |   
473 fBodyGyro.bandsEnergy.17.32 |   
474 fBodyGyro.bandsEnergy.33.48 |   
475 fBodyGyro.bandsEnergy.49.64 |   
476 fBodyGyro.bandsEnergy.1.24  |   
477 fBodyGyro.bandsEnergy.25.48 |   
478 fBodyGyro.bandsEnergy.1.8.1 |   
479 fBodyGyro.bandsEnergy.9.16.1    |   
480 fBodyGyro.bandsEnergy.17.24.1   |   
481 fBodyGyro.bandsEnergy.25.32.1   |   
482 fBodyGyro.bandsEnergy.33.40.1   |   
483 fBodyGyro.bandsEnergy.41.48.1   |   
484 fBodyGyro.bandsEnergy.49.56.1   |   
485 fBodyGyro.bandsEnergy.57.64.1   |   
486 fBodyGyro.bandsEnergy.1.16.1    |   
487 fBodyGyro.bandsEnergy.17.32.1   |   
488 fBodyGyro.bandsEnergy.33.48.1   |   
489 fBodyGyro.bandsEnergy.49.64.1   |   
490 fBodyGyro.bandsEnergy.1.24.1    |   
491 fBodyGyro.bandsEnergy.25.48.1   |   
492 fBodyGyro.bandsEnergy.1.8.2 |   
493 fBodyGyro.bandsEnergy.9.16.2    |   
494 fBodyGyro.bandsEnergy.17.24.2   |   
495 fBodyGyro.bandsEnergy.25.32.2   |   
496 fBodyGyro.bandsEnergy.33.40.2   |   
497 fBodyGyro.bandsEnergy.41.48.2   |   
498 fBodyGyro.bandsEnergy.49.56.2   |   
499 fBodyGyro.bandsEnergy.57.64.2   |   
500 fBodyGyro.bandsEnergy.1.16.2    |   
501 fBodyGyro.bandsEnergy.17.32.2   |   
502 fBodyGyro.bandsEnergy.33.48.2   |   
503 fBodyGyro.bandsEnergy.49.64.2   |   
504 fBodyGyro.bandsEnergy.1.24.2    |   
505 fBodyGyro.bandsEnergy.25.48.2   |   
506 fBodyAccMag.mean    |   
507 fBodyAccMag.std |   
508 fBodyAccMag.mad |   
509 fBodyAccMag.max |   
510 fBodyAccMag.min |   
511 fBodyAccMag.sma |   
512 fBodyAccMag.energy  |   
513 fBodyAccMag.iqr |   
514 fBodyAccMag.entropy |   
515 fBodyAccMag.maxInds |   
516 fBodyAccMag.meanFreq    |   
517 fBodyAccMag.skewness    |   
518 fBodyAccMag.kurtosis    |   
519 fBodyBodyAccJerkMag.mean    |   
520 fBodyBodyAccJerkMag.std |   
521 fBodyBodyAccJerkMag.mad |   
522 fBodyBodyAccJerkMag.max |   
523 fBodyBodyAccJerkMag.min |   
524 fBodyBodyAccJerkMag.sma |   
525 fBodyBodyAccJerkMag.energy  |   
526 fBodyBodyAccJerkMag.iqr |   
527 fBodyBodyAccJerkMag.entropy |   
528 fBodyBodyAccJerkMag.maxInds |   
529 fBodyBodyAccJerkMag.meanFreq    |   
530 fBodyBodyAccJerkMag.skewness    |   
531 fBodyBodyAccJerkMag.kurtosis    |   
532 fBodyBodyGyroMag.mean   |   
533 fBodyBodyGyroMag.std    |   
534 fBodyBodyGyroMag.mad    |   
535 fBodyBodyGyroMag.max    |   
536 fBodyBodyGyroMag.min    |   
537 fBodyBodyGyroMag.sma    |   
538 fBodyBodyGyroMag.energy |   
539 fBodyBodyGyroMag.iqr    |   
540 fBodyBodyGyroMag.entropy    |   
541 fBodyBodyGyroMag.maxInds    |   
542 fBodyBodyGyroMag.meanFreq   |   
543 fBodyBodyGyroMag.skewness   |   
544 fBodyBodyGyroMag.kurtosis   |   
545 fBodyBodyGyroJerkMag.mean   |   
546 fBodyBodyGyroJerkMag.std    |   
547 fBodyBodyGyroJerkMag.mad    |   
548 fBodyBodyGyroJerkMag.max    |   
549 fBodyBodyGyroJerkMag.min    |   
550 fBodyBodyGyroJerkMag.sma    |   
551 fBodyBodyGyroJerkMag.energy |   
552 fBodyBodyGyroJerkMag.iqr    |   
553 fBodyBodyGyroJerkMag.entropy    |   
554 fBodyBodyGyroJerkMag.maxInds    |   
555 fBodyBodyGyroJerkMag.meanFreq   |   
556 fBodyBodyGyroJerkMag.skewness   |   
557 fBodyBodyGyroJerkMag.kurtosis   |   
558 angletBodyAccMean.gravity   |   
559 angletBodyAccJerkMean.gravityMean   |   
560 angletBodyGyroMean.gravityMean  |   
561 angletBodyGyroJerkMean.gravityMean  |   
562 angleX.gravityMean  |   
563 angleY.gravityMean  |   
564 angleZ.gravityMean  |   



## Transformations

The **features.txt** file was read and the result was a data frame of column names. This was edited to standarize appearance as noted above.

The **activity_labels.txt** file was read into the data frame **activities**.

The testing and training data were acquired in separate operations. First, subject and activity information was for the type of activity was read into separate data frames (**test_subjects** and **test_activity**). Then the data was read. The three data frames one were then combined using cbind. At this time a new column, **type**, was also introduced to distinguish between "test" and "train" sets when all the data was eventually combined. Column names were added using the **features** data frame as the column names. This resulted in the data frame **test_complete**.The process was repeated for the training data.

rbind was then used to combine the test and training data into one dataset, **completeData**.

The **activities** data frame was then used to convert the column **activity** in **completeData** from an integer to a factor, providing text descriptions of each type of activity.

A select command was then used to extract columns of interest, which were **subject**, **activity** and any column containing either "mean" or "std", and stored in **subsetData**.

**subsetData** was then grouped by **subject** and **activity** and the summarize_each command was used to compute the mean of all the columns containing mean or standard deviation data. The result was stored in the data frame **tidyData**.

This column names that had been computed were then prefixed with "avg." to indicate that the information represented the mean of the original data.

**tidyData** was then written to a file using write.table .

