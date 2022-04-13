# HEN-analysis
A Study oriented projected related to HEN analysis.

This report covers the explanation of heat exchange network which exploits excess heat by integrating process hot and cold streams and improves energy efficiency by reducing utility usage and developed a program which performs first law analysis and  pinch analysis on the input stream data and provides the necessary results for inferring the maximum heat recovery and minimum energy consumption in the effort to increase economic feasibility. 

The generic assumptions and heuristics for the mathematical approach to heat exchange network analysis were assumed. Python was used to develop the code using the libraries - Pandas, NumPy, Matplotlib, SciPy and PyPinch. Pinch temperature, hot and cold utility and composite curves were assessed by the code. The mathematics required for building an optimization algorithm for solving the minimum matches problem to find the minimum number of heat exchangers was explained.


# What is HEN-analysis:

> HEN is networks of heat exhangers used to transfer heat from multiple hot streams to multiple cold streams. Heat exchanger network (HEN) is an important  
> technique for maximizing heat recovery in the industrial chemical process and reducing external heating and cooling utilities.

<img width="398" alt="Screenshot 2022-04-13 at 9 33 49 PM" src="https://user-images.githubusercontent.com/73723279/163222654-ddd251c2-4fdf-45ce-acd3-2c11320f8240.png">


# Pinch Analysis technique (PAT)

> Designing a Heat Exchangers Network [HEN] by application of pinch analysis is an effective >technique for energy integration 
>The technique estimates the minimum hot and cold utilities and the pinch point by the construction of a problem table and composite curves.
>Using PAT for HEN anlysis usually results in 20% energy savings.


# How does the code work:



https://user-images.githubusercontent.com/73723279/163225769-7610c6ba-f31c-4a1c-97da-a6d5dc5632c3.mp4



The working is explained using a flowsheet:


<img width="728" alt="Screenshot 2022-04-13 at 9 38 45 PM" src="https://user-images.githubusercontent.com/73723279/163223547-2c750e35-b37b-4c43-9f3d-706ea84eb8fd.png">

> The results obtained from it are listed below:
> - Problem Table
> - Cascade Anlaysis
> - Pinch Grid Representation
> - Composite Curves

# Problem Table:

Gives the energy balance for each temperature interval, labelling  them as 'surplus' for heat rejected to cold utility and 'deficit' for heat taken from hot utility.

> `pinch.constructProblemTable()
pinch.showPlots()`

> <img width="341" alt="Screenshot 2022-04-13 at 9 58 30 PM" src="https://user-images.githubusercontent.com/73723279/163227086-5987a614-4ebe-437a-89bf-fb60bfddeca0.png">


# Cascade Analysis:

Derives the minimum hot and cold utility requirements as per the feasibility.

> `pinch.constructHeatCascade()
pinch.showPlots()`

> <img width="429" alt="Screenshot 2022-04-13 at 9 59 21 PM" src="https://user-images.githubusercontent.com/73723279/163227199-3356f98c-8657-4447-a9ef-a66b34d85857.png">



# Pinch in grid representation

The graph gives the location of pinch in the temperature intervals which is important for determining number of minimum number of heat exchangers above and below pinch.

> `Pinch_in_the_grid_representation()`

> <img width="626" alt="Screenshot 2022-04-13 at 10 00 18 PM" src="https://user-images.githubusercontent.com/73723279/163227383-f2e817a3-8937-4f83-aa9c-72a357cc3a39.png">



# Composite Curve

The grand composite curve gives us the heat transfer between various temperature intervals We cascade heat to lower temperature intervals in intervals where there is a net heat excess.

Within each temperature interval, the grand composite curve provides a graphical representation of
the extra heat accessible to a process.

The grand composite curve is essential for optimizing the heat exchanger network.

> `pinch.constructShiftedCompositeDiagram()
pinch.showPlots()`

> <img width="445" alt="Screenshot 2022-04-13 at 10 00 52 PM" src="https://user-images.githubusercontent.com/73723279/163227465-d84c3c97-874f-4074-bf47-163ac49d32b8.png">

> <img width="445" alt="Screenshot 2022-04-13 at 10 01 29 PM" src="https://user-images.githubusercontent.com/73723279/163227580-828e6969-1d04-4589-8ef7-1ded5be64e99.png">

> <img width="445" alt="Screenshot 2022-04-13 at 10 01 39 PM" src="https://user-images.githubusercontent.com/73723279/163227610-0f915910-9cda-48a4-8be3-cc4448fba5e2.png">


# Future Prospects:

The minimum number of heat exchangers required can be found by employing an optimisation algorithm to eliminate all the loops in the heat exchanger network this is done by the MINLP optimisation algorithm. The mathematical model on which the algorithm is based on matching the stream energies . 






























