# syntenyPlotByR<br>
plot synteny genome alignment by mapper Mummer or LastZ using syntenyPlot.R.<br>
plot assemblies comparison using comparePlot.R <br>
<br>
###########<br>
requriement<br>
###########<br>
R 3.3+<br>
optparse # an R package <br>
<br>
###########<br>
plot mummer delta file<br>
###########<br>
There is a sample delta file and an output named "out.png" in project. user could try this by yourself.<br> 
<i>Rscript syntenyPlot.R -i <delta.file> -o out.png</i><br>
<br>
###########<br>
Large delta file<br>
###########<br>
If the delta file is too large, it is very time-consuming for ploting it. We recommand format the delta file by our PERL script firstly. And then plot the format delta file.<br>
<i>perl nucmer2RPlotFormat.pl <delta.file> >out.format</i><br>
<i>Rscript syntenyPlot.R -i <delta.file> -c -o out.png</i><br>
<b>If the delta is formatted, the parameter -c should be setted.</b><br>
<br>
###########<br>
LastZ<br>
###########<br>
There are two steps to format LastZ into our plot format. Only support one chromosome in Reference right now.<br>
<i>perl maf2R_01.pl *.maf >out.maf_1</i><br>
<i>perl maf2R_02.pl *out.maf_1 >out.maf_2</i><br>
<i>Rscript syntenyPlot.R -i <out.maf_2> -c -o out.png</i><br>
<b>If the delta is formatted, the parameter -c should be setted.</b><br>

###########<br>
R Plot Format <br>
###########<br>
There are 11 columns in Our R plot Format. User could change any alignment format into our R plot format and then plot it by our R script. And there is a sample file named "out.format" in project.<br>
<p>
refid # 1st columns <br>
qryid # 2nd columns <br>
reflen # 3rd columns <br>
qrylen # 4th columns<br>
refstart # 5th columns<br>
refend # 6th columns<br>
qrystart # 7th columns<br>
qryend # 8th columns<br>
refollen # 9th columns<br>
belong ref start # 10th columns<br>
belong ref # 11th columns<br>
</p>

###########<br>
Plot assemblies comparison <br>
###########<br>
There is a sample of three alignment files using minimap and an output named "AssemblyCompare.png" in project. user could try this by yourself.<br> 
<i>Rscript comparePlot.R -i <alignment.files> -o out.png</i><br>
<br>
<br><br>