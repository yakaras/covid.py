# covid.py
A covid-19 spreading simulation with real parameters
<br/><br/>
[![Product Name Screen Shot][product-screenshot]](https://ara-systems.net)

### Installation

1. Clone the repo
   ```sh
   git clone https://github.com/iion91/covid.py.git
   ```
   or download the file
2. Install dependencies
   ```sh
   pip install numpy
   pip install matplotlib
   ```
3. Start the script 
   ```cmd
   python virus.py
   ```
### Explanation

The definded color constants ```GREY```, ```RED```, ```GREEN```, and ```BLACK```, represent different states of the population (uninfected, infected, recovered, and dead).
The code defines a dictionary ```COVID19_PARAMS``` that contains various parameters related to the COVID-19 virus. These parameters include the basic reproduction number (```r0```), incubation period, percentage of mild and severe cases, recovery periods for mild and severe cases, death periods for severe cases, fatality rate and serial interval.
The class Virus represents the simulation of virus spread. It has several methods and instance variables for initializing the plot, creating annotations, storing population and infection information, and simulating the spread of the virus.
The ```initial_population``` method sets up the initial population by creating a scatter plot of individuals on a polar coordinate system. One individual is marked as "patient zero" and assigned as the first infected case. The locations of infected individuals are stored in arrays ```thetas``` and ```rs```.
The ```spread_virus``` method is called repeatedly to update the spread of the virus on each iteration. It first determines the number of new infections based on the current infection status and the reproductive number. It randomly selects individuals to become newly infected and updates the infected population information.
The ```one_by_one``` method is used to animate the spread of the virus on each iteration. It updates the plot by adding infected individuals one by one, creating a visual representation of the spread.
The ```assign_symptoms``` method randomly assigns symptoms (mild or severe) to the newly infected individuals, considering the given parameterws. It also assigns recovery or death days for severe cases based on the recovery and death periods.
The ```update_status``` method updates the status of infected individuals based on their recovery or death days. Recovered individuals are marked as green, and dead individuals are marked as black.
The ```update_text``` method updates the text annotations on the plot to show the current day, number of infected, number of deaths, and number of recovered individuals.
The ```gen``` method is a generator function used to control the animation. It continues to yield as long as the total number of deaths and recoveries is less than the total number of infected individuals.
The animate method creates the animation by calling the FuncAnimation function from ```matplotlib.animation```. It uses the ```spread_virus``` method as the animation function and the ```gen``` method to control the frames.
Finally, the main function creates an instance of the Virus class with the provided COVID-19 parameters and calls the animate method to start the simulation. The simulation is displayed using ```plt.show()```.


   
### Usage
If you like, you can modify the script to show other virus behavior.

Example:
   ```python
   COVID19_PARAMS = {
    "r0": 2.28,
    "incubation": 5, #--> to 8 or something
    "percent_mild": 0.8,
    "mild_recovery": (7, 14),
    "percent_severe": 0.2,
    "severe_recovery": (21, 42),
    "severe_death": (14, 56),
    "fatality_rate": 0.034,
    "serial_interval": 7
   }
   ```

[product-screenshot]: images/screenshot.png
