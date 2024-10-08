```
    **@@ #========= @@**            ___                     _ 
      **@@ +----- @@**             / _ \  _ __ ___   _ __  (_)
        **@@ = @@**               | | | || '_ ` _ \ | '_ \ | |
           **@@                   | |_| || | | | | || | | || |
        @@** = **@@                \___/ |_| |_| |_||_| |_||_|
     @@** ------+ **@@                
   @@** =========# **@@            ____  
  @@ ---------------+ @@          / ___|  ___  _ __    ___   _ __ ___    ___ 
 @@ ================== @@        | |  _  / _ \| '_ \  / _ \ | '_ ` _ \  / _ \
  @@ +--------------- @@         | |_| ||  __/| | | || (_) || | | | | ||  __/ 
   @@** #========= **@@           \____| \___||_| |_| \___/ |_| |_| |_| \___| 
    @@** +------ **@@         
       @@** = **@@           
          @@**                    ____                      _   
       **@@ = @@**               | __ )   ___  _ __    ___ | |__  
    **@@ -----+  @@**            |  _ \  / _ \| '_ \  / __|| '_ \ 
  **@@ ==========# @@**          | |_) ||  __/| | | || (__ | | | |
  @@ --------------+ @@**        |____/  \___||_| |_| \___||_| |_|
```
# OmniGenBench: Automating Large-scale in-silico Benchmarking for Genomic Foundation Models

# Introduction
The advancements in artificial intelligence in recent years, such as Large Language Models (LLMs), have fueled expectations for breakthroughs in genomic foundation models (GFMs). The code of nature, hidden in diverse genomes since the very beginning of life's evolution, holds immense potential for impacting humans and ecosystems through genome modeling. Recent breakthroughs in GFMs, such as Evo, have attracted significant investment and attention to genomic modeling, as they address long-standing challenges and transform in-silico genomic studies into automated, reliable, and efficient paradigms. In the context of this flourishing era of consecutive technological revolutions in genomics, GFM studies face two major challenges: the lack of GFM benchmarking tools and the absence of open-source software for diverse genomics. These challenges hinder the rapid evolution of GFMs and their wide application in tasks such as understanding and synthesizing genomes, problems that have persisted for decades. To address these challenges, we introduce GFMBench, a framework dedicated to GFM-oriented benchmarking. GFMBench standardizes benchmark suites and automates benchmarking for a wide range of open-source GFMs. It integrates millions of genomic sequences across hundreds of genomic tasks from four large-scale benchmarks, democratizing GFMs for a wide range of in-silico genomic applications. 

# What you can do with OmniGenome
- Click-to-run tutorials of Genomic sequence modeling
- Automated benchmarking of genomic foundation models
- Instant inference using pre-trained checkpoints
- Customizable pipeline for genomic modeling tasks

# Installation
before installing OmniGenome, you need to install the following dependencies:
- Python 3.9+
- PyTorch 2.0+
- Transformers 4.37.0+

- To install OmniGenome, you can use pip:
```bash
pip install omnigenome -U
```
or you can clone the repository and install it from source:
```bash
git clone https://github.com/yangheng95/OmniGenome.git
cd OmniGenome
pip install -e .
```

# Quick Start

## Auto-benchmark for genomic foundation models (a.k.a., pretrained models)
```python3
from omnigenome import AutoBench
gfm = 'LongSafari/hyenadna-medium-160k-seqlen-hf'
# bench_root could be "RGB", "GB", "PGB", "GUE", which will be downloaded from the Hugging Face model hub
bench_root = "RGB"
bench = AutoBench(bench_root=bench_root, model_name_or_path=gfm, overwrite=False)
bench.run(autocast=False, batch_size=bench_size, seeds=seeds)
```

## RNA Design
```python3
from omnigenome import OmniGenomeModelForRNADesign  # Assuming this is where the model class is defined
 
# Initialize the model for RNA design
model = OmniGenomeModelForRNADesign(model_path="anonymous8/OmniGenome-186M")

# Define the target RNA structure
structure = "(((....)))"  # Example of a simple RNA hairpin structure

# Run the genetic algorithm to design RNA sequences
best_sequences = model.run_rna_design(structure=structure, mutation_ratio=0.5, num_population=100, num_generation=100)

# Print the best sequence(s)
print("Best RNA sequences:", best_sequences)
```

# Tutorials
Please find more usage tutorials in [examples/tutorials](https://github.com/yangheng95/OmniGenomeBench/tree/master/examples/tutorials).



# License
OmniGenomeBench is licensed under the Apache License 2.0. See the LICENSE file for more information.

# Citation
```bibtex
@misc{yang2024omnigenbenchautomatinglargescaleinsilico,
      title={OmniGenBench: Automating Large-scale in-silico Benchmarking for Genomic Foundation Models}, 
      author={Heng Yang and Jack Cole and Ke Li},
      year={2024},
      eprint={2410.01784},
      archivePrefix={arXiv},
      primaryClass={q-bio.GN},
      url={https://arxiv.org/abs/2410.01784}, 
}
```

