# Linewidth Parameter Search System

(Standalone Desktop Application User Guide)

A standalone desktop application for linewidth experimental data analysis — enabling automatic PDF conversion, Bayesian optimization-based parameter fitting, and visual result comparison.

## Quick Start

1. Launch the Application

​	Locate the compiled executable file (`linewidth_finalversion1.exe`) in your directory.

​	Double-click the file to launch the application (no Python environment required).

2. Load Linewidth Data

   1. In the top control bar, click the ***"1. Load Frequency Data"*** button.

   2. Select your data file (supports `.xlsx `/` .csv` format):

      ***\*File Requirement\****: The file must contain 2 numeric columns:

      ​	1st column: Linewidth values (Hz)

      ​	2nd column: Corresponding frequency counts

   3. After successful loading:

      The selected file name will display next to the button (truncated if longer than 25 characters).

      The ***"2. Start Search"*** button will be activated.

3. Set Intensity Parameter

    1. Enter an integer in the ***"Intensity"*** input box (default value: 200):

        This value controls the iteration count for Bayesian optimization.

        Larger values (e.g., 300-500) improve fitting precision but increase runtime.

        Smaller values (e.g., 100) speed up processing but may reduce accuracy.

    2. The integer specified in the ***"Gauss Deg"*** input box defines the integration order used for the calculation.

        The default value is 40 and usually does not need to be changed.

        If noticeable local fluctuations appear in the fitted curve, the value can be increased accordingly (e.g., to 100).

4. Run Parameter Search

   1. Click the ***"2. Start Search"*** button (the button will show "Running..." and disable during processing).

   2. The system will automatically execute:

​		Data cleaning and frequency-to-PDF conversion

​		Intelligent parameter range determination

​		Bayesian optimization 

​		Parameter validity check and adjustment

5. View & Save Results

    1. Result Logs

       The left panel displays real-time processing logs and final parameters ($\gamma_1$, $\gamma_2$, $\sigma_1$, $\sigma_2$) under the **[Final Results]** section.

       Focus on the ***RSE value*** (smaller = better fitting effect).

    2. Visualization

       The right plot panel shows:

       ​	Orange bars: Experimental linewidth data

       ​	Blue line: Fitted curve (title includes RSE value)

       Click the save icon on the plot window to export the figure (supports `.png`/`.pdf`).

## Key Features

+ Standalone application (no Python/environment dependencies)

+ Multi-format data support (`.xlsx`/`.csv`)

+ Automatic frequency-to-PDF conversion

+ Bayesian optimization for high-precision fitting

+ Real-time log and visual result display

+ Parameter validity check for physical rationality

## Important Notes

+ Ensure the data file columns are in the correct order (Linewidth → Frequency).

+ For .csv files, use comma (`,`) or tab (`\t`) as separators (convert other separators first).

+ Do not close the application window during processing (will terminate the calculation).
+ If fitting effect is poor (high RSE):

​		Check data quality (remove outliers)

​		Increase the Intensity value and re-run.
