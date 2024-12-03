# Algorithmic trading


## Part 1. Interpolation of tabulated functions

You need to plot a tabulated function of stock quotes using interpolation methods:

- The program must be developed in C++ language of C++17 standard
- The library code must be located in the src folder in the develop branch
- When writing code it is necessary to follow the Google style
- The program must be built with Makefile which contains standard set of targets for GNU-programs all, install, uninstall, clean, dvi, dist. Installation directory could be arbitrary, except the building one
- GUI implementation, based on any GUI library with API for C++ (Qt, SFML, GTK+, Nanogui, Nngui, etc.)
- The data are loaded into the program from a file with stock quotes with the .csv extension:
    -  The file contains data in the form of a table, where the first column is the date, the second column is the value of the function (examples of data files are in the materials folder)
- When uploading a new data file, clear the field for drawing graphs
- The user sets the number of points on which the graph should be plotted (the number of points is not less than in the loaded file)
- All points are evenly distributed between the start and end dates
- On the final graph adjacent points must be connected by a straight line
- Two interpolation methods must be implemented: *Cubic Spline* and *Newton's Polynomial of nth degree*.
- There should be a button in the interface for drawing the cubic spline graph
- There should be a button in the interface for drawing the graph by the Newton polynomial of nth degree
- There should be a field in the interface for entering the degree of the Newton polynomial
-  There should be a button in the interface for clearing the field to draw graphs (the field is cleared only when you click on this button or new data is uploaded)
- There can be up to 5 graphs displayed in the field at the same time (all graphs have different color)
- If there are already 5 graphs displayed in the field, the buttons for drawing new graphs must be blocked
- The interface has to contain the following information about the graphs:
    - Color
    - Name of the file from which the data were taken
    - Interpolation method (specifying the degree if it is a Newton polynomial)
- Provide the ability to output the values of the stock quotes function obtained by both interpolation methods according to a user-defined argument value (date and time)

## Part 2. Approximation of tabulated functions

You need to plot a tabulated function of stock quotes using the *least squares method*. \
Moreover, the graph should cover a longer period of time than the input data:

- For graphs from this task there should be a separate field in the interface for drawing
- When uploading a new data file, clear the field for drawing graphs
- The user sets the number of points on which the graph should be plotted (the number of points is not less than in the loaded file)
- All points are evenly distributed between the start and end dates
- On the final graph adjacent points must be connected by a straight line
- On the graph, the points specified in the loaded file must be visually marked:
    - The radius of these points is larger than the thickness of the graph curve
    - The color of these points are differ from colors of the graphs in the field
- The user sets the number of days `M` for which we want to extend the graph (how many days ahead we want to predict the stock price)
- Clear the drawing field when adding a new approximation graph, in which `M` differs from `M` of already drawn graphs
- There can be up to 5 graphs with the same value of the number of days `M` displayed in the field at the same time
  (all graphs should have different color)
- There should be a button in the interface for drawing the graph plotted by the polynomial of the degree set at that time
- There should be a field in the interface for entering the degree of the polynomial
- There should be a button in the interface for clearing the field to draw the approximation graphs
- The interface has to contain the following information about the graphs:
    - Color
    - Name of the file from which the data were taken
    - Degree of polynomial
- If there are already 5 graphs displayed in the field, the buttons for drawing new graphs must be blocked
- Provide the ability to display the value of the approximating function for a given degree of the polynomial according to the user-defined value of the argument (date and time)

## Part 3. Bonus. Research on temporal characteristics

Study the temporal characteristics of interpolations by cubic spline and Newton polynomial methods, depending on the number of calculated points.

- The user sets the maximum number of points `k` and the number of partitions `h`.
- The minimum number `k` is the number of entries in the input table
- You need to measure the time required to calculate values using the spline interpolation algorithms and Newton's method, depending on the change in the number of points.  There must be a total of `h` measurements of the algorithm runtime, the first of which is the measurement for $`k_1`$, where $`k_1`$ equals the number of points in the source file, and the last is $`k_h`$, where $`k_h`$ equals the maximum number of points `k` that is entered through the GUI.
- Measurement of time at each iteration should be performed 10 times and the result should be the arithmetic mean of the obtained values
- In the same field plot two graphs showing the dependencies of the time required to find values from the number of points `k` for two interpolation methods

**Example** \
The user sets the number of points *k = 1000000* and the number of partitions *h = 11*.  A file containing 100 entries is inputted, then the average running time of the spline and Newton interpolation algorithms will be calculated for the next number of points:

    k1 = 100, t1_spline = <average_time_for_calculating_100_points_by_splines>, t1_newton = <average_time_for_calculating_100_points_by_Newton’s_method> 
    k2 = 100090, t2_spline = <average_time_for_calculating_100090_points_by_splines>, t2_newton = <average_time_for_calculating_100090_points_by_Newton’s_method> 
    k3 = 200080, t3_spline = <average_time_for_calculating_200080_points_by_splines>, t3_newton = <average_time_for_calculating_200080_points_by_Newton’s_method> 
    k4 = 300070, t4_spline = <average_time_for_calculating_300070_points_by_splines>, t4_newton = <average_time_for_calculating_300070_points_by_Newton’s_method> 
    k5 = 400060, t5_spline = <average_time_for_calculating_400060_points_by_splines>, t5_newton = <average_time_for_calculating_400060_points_by_Newton’s_method> 
    k6 = 500050, t6_spline = <average_time_for_calculating_500050_points_by_splines>, t6_newton = <average_time_for_calculating_500050_points_by_Newton’s_method> 
    k7 = 600040, t7_spline = <average_time_for_calculating_600040_points_by_splines>, t7_newton = <average_time_for_calculating_600040_points_by_Newton’s_method> 
    k8 = 700030, t8_spline = <average_time_for_calculating_700030_points_by_splines>, t8_newton = <average_time_for_calculating_700030_points_by_Newton’s_method> 
    k9 = 800020, t9_spline = <average_time_for_calculating_800020_points_by_splines>, t9_newton = <average_time_for_calculating_800020_points_by_Newton’s_method> 
    k10 = 900010, t10_spline = <average_time_for_calculating_900010_points_by_splines>, t10_newton = <average_time_for_calculating_900010_points_by_Newton’s_method> 
    k11 = 1000000, t11_spline = <average_time_for_calculating_1000000_points_by_splines>, t11_newton = <average_time_for_calculating_1000000_points_by_Newton’s_method> 

The result will be two graphs, each consisting of 11 points:
* the dependence of the number of points `k` from `t_spline`
* the dependence of the number of points `k` from `t_newton`

## Part 4. Bonus. Approximation with weights

Add weights to the table function of stock quotes and take them into account when plotting graphs.

- Add the 3rd column to the source data files: point weights
- For all values that have no weight specified, it is considered equal to 1
- Adapt the method of least squares so that it takes into account the weights of points
- Add the ability to plot the following 4 graphs simultaneously:
    - With the degree of polynomial 1 for a table with user-defined weights
    -  With the degree of polynomial 2 for a table with user-defined weights
    -  With the degree of polynomial 1 for a table in which all weights are 1
    -  With the degree of polynomial 2 for a table in which all weights are 1
- Find the weights that change the sign of the slope of the line corresponding to degree 1 of the polynomial
- Save the file part4.csv to the src folder in the repository, where the weights are set so that the condition of the previous point is met

__*__ - This is not an investment recommendation.
