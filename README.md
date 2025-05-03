
# Simplified Phasmatodea Population Evolution (PPE) Algorithm

[![Stargazers](https://img.shields.io/github/stars/spcity/Simplified-Phasmatodea-population-evolution-algorithm-PPE?style=social)](https://github.com/YOUR_USERNAME/YOUR_REPOSITORY/stargazers)
[![Visitors](https://api.visitorbadge.io/api/visitors?path=https%3A%2F%2Fgithub.com%2Fspcity%2FSimplified-Phasmatodea-population-evolution-algorithm-PPE&countColor=%23263759&style=flat)](https://github.com/YOUR_USERNAME/YOUR_REPOSITORY)
## 📜 Overview

This repository contains the MATLAB implementation of the **Simplified Phasmatodea Population Evolution (PPE)** algorithm, as presented in the paper:

> Song, P., Chu, S., Pan, J. et al. Simplified Phasmatodea population evolution algorithm for optimization. *Complex Intell. Syst.* 8, 673–694 (2022). https://doi.org/10.1007/s40747-021-00402-0

PPE is a metaheuristic optimization algorithm inspired by the unique survival strategies and evolutionary behaviors of Phasmatodea (stick insects). This simplified version aims to provide an efficient and effective approach for solving complex optimization problems.

## ✨ Innovation and Advantages

Based on the referenced paper and the provided code:

* **Simplicity:** Offers a streamlined structure compared to potentially more complex metaheuristics, making it easier to understand and implement.
* **Inspired Mechanism:** Leverages concepts like population density dynamics (logistic map-like updates `Px`, `Pa`), individual tendency (`A`), guidance from multiple local optima (`L_pha`), mutation (`tubian`), and competition/coexistence mechanisms to navigate the search space.
* **Balanced Search:** Integrates mechanisms for both exploration (mutation, competition response) and exploitation (attraction towards nearest local best `choosebest`) to effectively seek global optima.
* **Effectiveness:** Demonstrated performance on benchmark optimization functions (e.g., CEC suites as implemented in `main.m`).

## 🚀 How to Use the Code

This implementation is written in MATLAB.

**1. Prerequisites:**
    * MATLAB installed.
    * (Potentially) A C++ compiler configured for MATLAB (`mex -setup`) if you need to recompile the benchmark function `.cpp` files (e.g., `cec13_func.cpp`, `cec14_func.cpp`, `cec17_func.cpp`). Compiled versions might be needed depending on your system.
    * Benchmark function data files (e.g., `input_data` folders for CEC benchmarks) available in the correct path if using specific test suites like CEC2017.

**2. Configuration (`main.m`):**
    * Open the `main.m` file.
    * **Set Parameters:**
        * `D`: Dimension of the problem.
        * `pop_size`: Number of individuals in the population.
        * `FES`: Maximum number of Fitness Evaluations (used to calculate `Max_Gen`).
        * `Xmin`, `Xmax`: Lower and upper bounds of the search space.
        * `runs`: Number of independent runs for statistical analysis.
    * **Select Benchmark Function:**
        * Uncomment the desired benchmark suite (e.g., `fhd=str2func('cec13_func'); Fnum = 28;`).
        * Ensure the corresponding `.cpp` file is compiled and accessible to MATLAB.

**3. Running the Algorithm:**
    * Run the `main.m` script from the MATLAB command window or editor.
    * `>> main`

**4. Output:**
    * The script will iterate through the selected benchmark functions (`Fnum`) for the specified number of `runs`.
    * The best fitness value (`Fit_min`) found in each run will be printed to the MATLAB console.
    * The core function `PEO_12_6_func.m` returns:
        * `Gbest`: The best solution vector found.
        * `Fit_min`: The fitness value of the best solution.
        * `fit_save` (in `main.m`): A vector containing the best fitness value found at each generation/iteration (convergence curve).

```matlab
% Example call within main.m
[Gbest, Fit_min, fit_save] = PEO_12_6_func(fhd, D, pop_size, FES/pop_size, Xmin, Xmax, func_num);
Fit_min % Prints the final best fitness for the run
```

## 📚 Related Publications & Citations

Here is a list of publications related to the Phasmatodea Population Evolution algorithm and its variants:

* Han, S., Chen, S., Yan, F., Pan, J., & Zhu, Y. (2023). A Hybrid Parallel Balanced Phasmatodea Population Evolution Algorithm and Its Application in Workshop Material Scheduling. *Entropy*.
* Pan, J., Zhang, M., Chu, S., Xue, X., & Snásel, V. (2025). Phasmatodea Population Evolution Algorithm Based on Spiral Mechanism and Its Application to Data Clustering. *Computers, Materials & Continua*.
* Zhang, AN., Chu, S., Song, PC., Wang, H., & Pan, JS. (2022). Task Scheduling in Cloud Computing Environment Using Advanced Phasmatodea Population Evolution Algorithms. *Electronics*, *11*(9), 1478. (Cited: 20)
* Wu, TY., Li, H., & Chu, S. (2023). CPPE: An Improved Phasmatodea Population Evolution Algorithm with Chaotic Maps. *Mathematics*, *11*(8), 1957. (Cited: 19)
* Song, P., Chu, S., Pan, J., & Yang, H. (2021). Simplified Phasmatodea population evolution algorithm for optimization. *Complex & Intelligent Systems*, *8*, 673–694. (DOI: 10.1007/s40747-021-00402-0) (Cited: 42)
* Chu, S., Liang, L., Pan, J., Kong, L., & Zhao, J. (2024). Surrogate-assisted sine Phasmatodea population evolution algorithm applied to 3D coverage of mobile nodes. *Complex & Intelligent Systems*. (Cited: 1)
* Liang, L., Chu, S., Du, Z., & Pan, J. (2022). Surrogate-assisted Phasmatodea population evolution algorithm applied to wireless sensor networks. *Wireless Networks*, *29*, 681–699. (Cited: 8)
* Zhu, Y., Yan, F., Shi, Z., et al. (2022). Multigroup-Based Phasmatodea Population Evolution Algorithm with Multistrategy for IoT Electric Bus Scheduling. *Wireless Communications and Mobile Computing*, *2022*, 1-14. (Cited: 7)
* Song, P., Chu, S., Pan, J., & Yang, H. (2020). Phasmatodea population evolution algorithm and its application in length-changeable incremental extreme learning machine. *2020 2nd International Conference on Industrial Artificial Intelligence (IAI)*, 1-5. (Cited: 13)
* Zhuang, J., Chu, S., Hu, CC., Liao, L., & Pan, J. (2022). Advanced Phasmatodea Population Evolution Algorithm for Capacitated Vehicle Routing Problem. *Journal of Advanced Transportation*, *2022*. (Cited: 3)
* Lou, J., Chu, S., Pan, J., & Zhuang, Z. (2025). Time-varying Binary Phasmatodea Population Evolution Algorithm. *Journal of Internet Technology*.
* Ren, H., Feng, X., Sun, Q., & Xiong, L. (2024). Improved Phasmatodea Population Evolution Algorithm based on Dung Beetle Optimizer. *Proceedings of the 2024 International Conference on Machine Learning and Network Technology (MLNT 2024)*.
* Pan, JS., Song, PC., Pan, CA., & Abraham, A. (2021). The Phasmatodea Population Evolution Algorithm and Its Application in 5G Heterogeneous Network Downlink Power Allocation Problem. *Journal of Internet Technology*, *22*(6), 1241-1251. (Cited: 8)
