**Description** 

The R script ([./plot_kaks_err_bars.R][3]), calculates error bars for dN/dS (a.k.a. Ka/Ks) values, calculated for pairs of [orthologous][1] DNA sequences (i.e. pairs of genes of interest represented as their untranslated DNA sequences), one error bar per pair. The dN/dS values for each pair has to already be calculated by the [KaKs calculator][2], who will make an outputfile (e.g. [./example_kaks_output.txt][4]), only then will [./plot_kaks_err_bars.R][3] be able to generate the error bars (i.e. the output file of KakS calculator is the input file for [./plot_kaks_err_bars.R][3]). See below for instructions/requirements.

To help you explore your data, [./plot_kaks_err_bars.R][3] will make barplots of your dN/dS (a.k.a. Ka/Ks) values, adding the error bars onto each bar. One barplot per alternative dN/dS calculation method (e.g. NG, a.k.a. Nei-Gojobori method has its own barplot). X-axis: One bar per pair of DNA sequences (protein). Y-axis:  dN/dS with error bars. Running the script will prompt you for the location of the required [KaKs calculator][2] output file, in your system.

![alt text][logo]

--- 

**Requirements / How to use**

For this dish, You WILL need the following ingredients: 

 1. The [KaKs calculator][2], more specifically its output data file (e.g. [./example_kaks_output.txt][4]) is what this R script (./plot_kaks_err_bars.R) needs for error bar generation. 

 2. A pair (or multiple pairs) of [orthologous][1] DNA sequences in a format that [KaKs calculator][2] accepts, e.g. [./example_kaks_output.txt][4] has several pairs of HTLV-1 viral gene sequences' dN/dS values (each pair has one ortholog for HTLV-1 and one ortholog for STLV-1 virus). As well as there being a different dN/dS value for each protein (ortholog pair), there are also different dN/dS values for each dN/dS calculation method (e.g. NG means Nei-Gojobori method, one barplot per method and one bar per viral protein [ortholog pair]). But to be more specific, you might need each pair of orthologous sequences to be *already aligned*, read the docs for KaKs Calculator if you are not sure.  

You MIGHT also need:

 1. Windows (OR ubuntu).

 2. RStudio IDE, it's free (I have not used on any other IDE, maybe you don't need).

 3. Latest version of R (Only tested on 2014+ versions). 

You need to then follow this recipe: 

 1. Run the [KaKs calculator][2] (https://code.google.com/archive/p/kaks-calculator/), read the instructions and give the DNA sequences it needs.

 2. Run this R script ([./plot_kaks_err_bars.R][3]), which will then prompt you for an output data file (e.g. [./example_kaks_output.txt][4])(next step).

 3. Browse for your KaKs calculator [output file][4], select and click. There might be several output files generated by KaKs calculator, so here I have an example data file that you can use as a reference, it SHOULD work: [./example_kaks_calc_output.txt][4].

 4. All done! The plot can be shown interactively, or uncomment CTRL+F: "@PLOT" line in the script to save to .PNG file kaks_error_bars. See: [./plots/kaks.png][5] for an example.

--- 

**Details**

[**./plot_kaks_err_bars.R**][3]: Generates bar plots with error bars from KaKs Calculator's output file.

[**./example_kaks_output.txt**][4]: Input: an example of input for [./plot_kaks_err_bars.R][3], do not worry about comamnd-line arguments, it will interactively prompt you to browse for the file in your system. Keep in mind, this required input (to [./plot_kaks_err_bars.R][4]) is obtained as an output file by [KaKs calculator][2]. The format here is what you want to look for when you run [KaKs calculator][2] for your own DNA sequence pairs.

[**./plots/kaks.png**][5]: Final output: Example of a plot generated by [./plot_kaks_err_bars.R][3]. As well as there being a different dN/dS value for each gene (ortholog pair), there are also different dN/dS values for each dN/dS calculation method (e.g. NG means Nei-Gojobori method, one barplot per method and one bar per viral protein (orthologous DNA sequence pair))

---

If you find that something does not work, or you see a conceptual issue with the code please do not hesitate to make a message on the GitHub repo. 


[1]: http://homepage.usask.ca/~ctl271/857/def_homolog.shtml
[2]: https://code.google.com/archive/p/kaks-calculator/
[3]: https://github.com/a1ultima/kaks_error_bars/blob/master/plot_kaks_err_bars.R
[4]: https://github.com/a1ultima/kaks_error_bars/blob/master/example_kaks_output.txt
[5]: https://github.com/a1ultima/kaks_error_bars/blob/master/plots/kaks.png
[logo]: https://github.com/a1ultima/kaks_error_bars/blob/master/plots/kaks.png?raw=true "dN/dS values for HTLV-1 viral proteins (STLV-1 reference) calculated using different methods for dN/dS (one barplot per method)"