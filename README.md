# 6T SRAM
SRAM is a type of memory commonly used inside processors and other integrated circuits because it is fast. A standard SRAM cell uses six transistors (6T) to store one bit of information. One way to reduce the energy used by SRAM is to lower its supply voltage (VDD). However, if the voltage becomes too low, the SRAM cell can become slower or unreliable. It may have trouble holding its stored value, reading the value without accidentally changing it, or writing a new value.

Our project will experimentally study how lowering the supply voltage affects the reliability of a 6T SRAM cell. We will also test different methods and designs that may help mitigate effects of low voltage, and ways of operating SRAM at lower voltage. This follows directly from our earlier work, which identified voltage, transistor sizing, read stability, write ability, energy, and delay as connected SRAM design tradeoffs.


# 6T SRAM

SRAM is a type of memory commonly used inside processors and other integrated circuits because it is fast. A standard SRAM cell uses six transistors (6T) to store one bit of information. One way to reduce the energy used by SRAM is to lower its supply voltage (VDD). However, if the voltage becomes too low, the SRAM cell can become slower or unreliable. It may have trouble holding its stored value, reading the value without accidentally changing it, or writing a new value.

Our project will experimentally study how lowering the supply voltage affects the reliability of a 6T SRAM cell. We will also test different methods and designs that may help mitigate effects of low voltage, and ways of operating SRAM at lower voltage. This follows directly from our earlier work, which identified voltage, transistor sizing, read stability, write ability, energy, and delay as connected SRAM design tradeoffs.

## Social and Technology Impact

SRAM makes up a large share of the area of modern processors, mainly in the form of caches and register files, so it also accounts for a significant portion of their power consumption. Because SRAM is used in nearly every digital chip, even small improvements in its energy efficiency can add up across the billions of devices produced each year. Lowering the supply voltage is one of the most effective ways to save energy, since dynamic power scales roughly with the square of VDD. Understanding how far the voltage can be lowered before the cell fails is therefore directly useful to chip designers.

From a social perspective, more energy-efficient memory benefits battery-powered devices such as smartphones, wearables, wireless sensors, and implantable medical devices, where longer battery life improves usability and can reduce how often devices must be recharged or replaced. At a larger scale, data centers consume a growing share of global electricity, and much of that energy goes into computation and memory access. Reducing memory power can lower operating costs and the environmental impact of computing, including the demand for electricity and cooling.

Reliability is equally important. If an SRAM cell flips its stored value, fails to read correctly, or fails to write new data, the result can be incorrect computation or system crashes. In safety-critical applications such as automotive systems, medical equipment, and aerospace electronics, these errors can have serious consequences. Our project focuses on the balance between saving energy and keeping memory reliable, which helps show that low-power design cannot come at the cost of correct operation.

From a technology perspective, the problem becomes harder as transistors shrink. Smaller devices show more variation from one transistor to another, which reduces the stability margins of the 6T cell and makes low-voltage failures more likely. Techniques such as transistor sizing, read and write assist circuits, and alternative cell designs are active areas of research and are used in commercial processors. By experimentally studying these tradeoffs, our project connects textbook SRAM design concepts to real engineering decisions that influence the performance, cost, and energy use of future computing systems.

## Methods

We will simulate the 6T SRAM cell in Cadence Virtuoso with Spectre and automate the work with two sets of scripts: OCEAN for running simulations and Python for analyzing results.

### OCEAN Scripts

OCEAN is Cadence's scripting language for controlling Spectre simulations. Our OCEAN scripts will:

- Load each testbench (hold, read, and write) and set up the DC and transient analyses
- Sweep VDD from the nominal supply down toward the near-threshold region
- Sweep transistor sizing, including the cell ratio and pull-up ratio
- Run process corner and Monte Carlo simulations to capture variation
- Export waveforms and measured values to CSV files

This lets us run many simulations in batch mode with consistent settings and makes the results easy to reproduce.

### Python Scripts

The exported CSV data will be processed in Python using NumPy, pandas, and Matplotlib. Our Python scripts will:

- Calculate static noise margin (SNM) from butterfly curves
- Extract write margin, delay, and energy values
- Estimate failure rates from Monte Carlo results and find the minimum operating voltage (Vmin)
- Plot each metric versus VDD and compare across sizing choices and corners

Keeping simulation and analysis separate means we can change the analysis or plots without rerunning the simulations.

### Running
**TODO**


###
Changes must be made to a different branch then merged
