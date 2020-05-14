# Towards-a-reservation-lifetime
Survival analysis, statistical test, Kaplan-Meier estimator, Cox regression, R

## General dataset description:
The dataset is taken from the paper entitled **"Hotel booking demande dataset"** by Nuno Antonio *et al.* published in open access on ScienceDirect at https://doi.org/10.1016/j.dib.2018.11.126. 

The dataset is a set of two sub-datasets (we rename **H1_resort.csv, H2_CityHotel.csv** for convenience). Both dataset share the sames structure with 31 covariates describing 40060 observations for H1_resort, 79330 observations for H2_CityHotel. Each observation represents a resort booking (H1_resort), city hoel booking (H2_CityHotel) . Both datasets comprehend bookings between the 1st of July 2015 and the 31st of August 2017 in Portugal : resort at region of Algarve and hotel in Lisbon. The booking datasets are righ-censored by booking status (cancellation or not) associated with booking time. 

In the framework of this demonstration, I list below the relevant features involved in the analysis : 

Covariate | Type | Description      | 
:------- |:---------------- | :---------- | 
ADR  | Numeric | AverageDailyRate 
Adults  | Integer        | Number of adults
Babies   | Integer | Number of babies
Children   | Integer | Number of children
Deposit Type   | Categorical | Type of deposit. Three groups
DistributionChannel   | Integer | Booking distribution channel. Four groups 
IsCanceled   | Categorical | Value indicating if the booking was canceled (1) or not (0)
LeadTime   | Integer | Number of days that elapsed between the booking-arrival dates
ReservationStatus   | Categorical | Reservation last status. 
ReservationStatusDate | Date | Date of last status set. It permits to estimate the time between booking-cancellation dates
StaysInWeekendNights | Integer | Number of weekend nights booked/stays 
StaysInWeekNights | Integer |  Number of week nights booked/stays 

*More details about other features can be found in the article.*


## Workflow: 
The aim of this study is to analyse the survival risk (cancellation or no cancellation) of a (resort, city hotel) booking over the booking time. This allows to build a prediction model based on the robust analysis detailed in this report. The model will permit hotel managers to anticipate a risk of cancellation of a booking, to reorganize their planning and prepare overbooking situation.

Each part has a same number of sections and I take care of the dataset by following section-by-section plan:

    Data exploration: it consits of loading dataset, showing statistical summary and some vizualization to have an overview about the dataset. The idea behind of this section relies on the discussion about the censored data and features, which will be selected for the study.

    Survival analysis : the backbone of our report. I study patterns, possible tests and techniques which appear to be appropriate to the dataset characteristics.

    Machine Learning/prediction : selection of the "best" model with the help of stepwise tehnique. The selection is of course in the line with the survival analysis. Finally, the evaluation of the model was done by assessing ROC curves.
