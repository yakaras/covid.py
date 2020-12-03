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
### Usage
If you like, you can modify the script to show your own virus.
You´ll just know the params and change them

Example:
   ```python
   COVID19_PARAMS = {
    "r0": 2.28,
    "incubation": 5, --> to 8 or something
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
