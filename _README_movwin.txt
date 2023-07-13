Started 13 July 2023
By Lizzie
Moving window project


<><><><><><><><><><><><><>
<> Very short overview <>
<><><><><><><><><><><><><>

Using a package to detect the relevant climate period that phenological events are 'responding' to has become extremely popular, without a lot of testing how well it works. Given all the weird correlations within real climate data, there could be lots of weird stuff going on. 

What's the aim of this project?

Test for plant phenological events (but thinking more generally about other phenological events) how well the package seems to work. 

<><><><><><><><><><><><><>
<><> How to do this? <><>
<><><><><><><><><><><><><>

Lots of ways! I think one reason we did not finish this project before is that we jumped in on testing and analyses before we had a clear path of what to test. So step 1 should be a clear list of what tests to run -- including how we will compare output, and then implement that. 

My suggested paths in order of potential usefulness (be sure to think through how you will compare/analyse the results FIRST):

1) Take the PEP725 data or other phenological time series with matching climate data, run climwin and then SHUFFLE the dates of the phenology and see how similar or different the climwin results are. (This will likely take a while and would be a great first step to aim for completing.)
2) Using the same climate data, generate budburst dates based on a simple thermal sum (GDD) model and test how well the model predicts the model (for example, it should suggest sum is a good model and pick up the window we used perhaps?).
3) Same as (2) but also simulate a chilling response before the thermal sum. See if the model picks this up. 

* Important point * See Box 2 in van de Pol et al. 2016: This reviews two different ways to compare support for different models, with k-fold being WAY better so PLEASE SEE how results differ when using k-fold ("can be implemented in climwin by setting the argument ‘K’ in the slidingwin function to, for example, K = 10"). Similarly it seems important to do step 3a (pp 1250-1252) and see how that changes the answer.  

LOTS of potentially useful code here: https://github.com/lizzieinvancouver/decsens/tree/master/analyses/pep_analyses/simmonds_slidingwin and see an issue on this: https://github.com/lizzieinvancouver/decsens/issues/18

Well commented code for generating phenological event dates based on cues: 
https://github.com/temporalecologylab/labgit/blob/master/projects/decsenspost/decsensSimsMultCues.R

Other possible task that could be useful (later): 
Review papers citing van de Pol et al. 2016 or Simmonds et al. 2019 and see how they use the moving window approach, especially whether they do step 3a (pp 1250-1252) from van de Pol et al. 2016. 

One thing we did in 2019-2020 was to simulate our own climate data; I think that is less interesting and not that useful as natural climate data has lots of important patterns we may lose. 

<><><><><><><><><><><><><><><><><><><>
<><> Very first suggested steps <><>
<><><><><><><><><><><><><><><><><><><>

Read van de Pol et al. 2016, Bailey & van de Pol 2016 and Simmonds et al. 2019, then try out the main functions you expect to need from climwin in R.

Next, start a git issue on your first planned attack on the problem! (See suggested path (1) above, but if you have a better idea, just let me know!)