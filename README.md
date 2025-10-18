# CRISPR Diagnostics for Nigerian Neonatal Sepsis

I'm a medical lab scientist, and in my daily work I see the devastating impact of delayed sepsis diagnosis in newborns. I figured there had to be a faster way to do this, which is how I found *PathoGD* — a tool for designing CRISPR-based diagnostics. The researchers were using it for STI pathogens, and I was wondering if I could adapt it for neonatal sepsis in Nigeria.

## What I Set Out to Do

In Nigerian hospitals, we often wait 2-3 days for blood culture results while newborns with sepsis need immediate treatment. Doctors have to guess which antibiotics might work, which can lead to resistance and poor outcomes.

I wanted to see if I could use computational tools to design a faster diagnostic - one that could detect sepsis pathogens in hours instead of days, specifically for the bacterial strains we see here in Nigeria.

## The Technical Challenge

I quickly learned that bioinformatics tools don't just "work." *PathoGD* required installing dozens of dependencies, configuring complex environments, and troubleshooting endless errors. I spent months battling:

- **Ubuntu crashes** when analyzing large genome files
- **Google Colab resets** losing my progress  
- **GitHub Codespaces restrictions** blocking NCBI database access
- **Missing tools** like taxonkit and genometester4 that *PathoGD* needed

Each error felt like a dead end, but each solution taught me something new about how computational biology actually works.

## The Breakthrough

After months of troubleshooting, I finally got *PathoGD* running. I configured it to target Nigeria's most common neonatal sepsis pathogens:

- *Escherichia coli*
- *Klebsiella pneumoniae* 
- *Staphylococcus aureus*
- *Streptococcus agalactiae* (Group B Streptococcus)

I ran the genome availability check to see if there was enough data to work with. *PathoGD* searched NCBI's databases and found:

**Over 14,000 complete bacterial genomes** are available for these pathogens.

Since the data exists, it shows the concept is feasible.

## The Reality Check

Things didn’t go as smoothly as I hoped. When I tried to run the full CRISPR design analysis, the setup couldn’t keep up with the large number of genomes—over 14,000 in total. I kept facing issues like slow downloads, memory errors, and missing dependencies.
So the main challenge was the computing power I have access to, not the science itself.

## What This Project Actually Achieved

Even though I didn’t get to the stage of generating the final CRISPR designs, the project still proved a few key things:  

1. **The data is there** – There are enough Nigerian pathogen genomes available to design a diagnostic.  
2. **The tool works** – *PathoGD* can be configured to target neonatal sepsis pathogens.  
3. **The real issue is computing power** – The challenge wasn’t the science, it was the limited infrastructure.  

So, while I didn’t finish the full pipeline, I showed that the idea is workable. With stronger computing resources, this project could easily move from concept to an actual point of care diagnostic design.

## Technical Details

For those interested in the specifics, here's what I actually set up and ran:

### Configuration
I created custom configuration files that specified:
- Target pathogens: E. coli, K. pneumoniae, S. aureus, Group B Streptococcus  
- Non-target species: Enterobacter, Salmonella (to ensure specificity)
- Analysis parameters for CRISPR guide RNA design

### What Worked
✅ *PathoGD* pipeline installation
✅ Custom configuration for Nigerian pathogens  
✅ Genome availability check (14,000+ genomes confirmed)
✅ Started k-mer analysis approach

### What Didn't
❌ Full genome download and processing
❌ Final CRISPR guide RNA design generation
❌ Specificity validation against non-target species

## Project Structure

This repository contains:
- `README.md` - This project documentation
- `pathogd/` - The original *PathoGD* tool with my configurations
  - `config_neonatal_sepsis.txt` - My main configuration file
  - `nigeria_sepsis_results/` - Outputs from my analysis attempts
  - Various test results from different approaches

The `pathogd` folder is the original research tool I worked with. My contributions are the configurations and analysis attempts within that structure.

## Lessons Learned

This project reinforced that being a developer means learning whatever tools you need to solve real problems:

- **Persistence pays off**: Every technical hurdle taught me something new about system dependencies and configuration
- **Infrastructure awareness**: I learned to assess computational requirements early in project planning  
- **Domain knowledge matters**: My medical background helped me ask the right questions and configure the tool appropriately
- **Learning by doing**: Sometimes you have to dive into unfamiliar territory (like bioinformatics) to build the solution you envision

As a medical lab scientist building Python skills, this project showed me how technical and domain expertise can combine to address healthcare challenges.

## Technical Stack & Languages Used

While working with *PathoGD*, I encountered a mix of programming languages typical in bioinformatics:
- **Bash** for the main pipeline execution
- **R** for data analysis and visualization components  
- **Python** for various helper scripts and data processing

This exposed me to how complex scientific tools often combine multiple languages, and showed me where Python skills can integrate with existing bioinformatics workflows.

## References & Next Steps

**Tool Used:**  
*PathoGD*: an integrative genomics approach to primer and guide RNA design for CRISPR-based diagnostics  
Low, S.J., O'Neill, M., Kerry, W.J. et al. Communications Biology 8, 147 (2025)  
https://doi.org/10.1038/s42003-025-07591-1

**Potential Next Directions:**
- Complete the analysis with adequate computational resources
- Develop Python wrappers for bioinformatics pipelines  
- Build on these findings for actual diagnostic development

---

*This project demonstrates my approach to problem-solving: identify real healthcare challenges and learn whatever tools are needed to address them.*