# 🧬 GenoFlow: Modular De Novo Genome Assembly & Annotation Pipeline

[![Python](https://img.shields.io/badge/Python-3.8%2B-blue.svg)](https://python.org)
[![Jupyter](https://img.shields.io/badge/Jupyter-Compatible-orange.svg)](https://jupyter.org)
[![Colab](https://img.shields.io/badge/Google%20Colab-Ready-yellow.svg)](https://colab.research.google.com)
[![License](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)
[![DOI](https://img.shields.io/badge/DOI-pending-lightgrey.svg)]()

> **A comprehensive, modular, and user-friendly pipeline for de novo genome assembly and annotation that runs seamlessly on Jupyter Notebook and Google Colab**

## 🚀 **Quick Start**

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/engkinandatama/genoflow/blob/main/GenoFlow_Complete_Pipeline.ipynb)

```bash
# Clone the repository
git clone https://github.com/engkinandatama/genoflow.git
cd genoflow

# Launch Jupyter Notebook
jupyter notebook GenoFlow_Complete_Pipeline.ipynb
```

## 📋 **Overview**

GenoFlow is a modular bioinformatics pipeline designed to democratize genome assembly and annotation analysis. Whether you're a beginner researcher or an experienced bioinformatician, GenoFlow provides:

- **🔧 Modular Design**: Mix and match tools based on your needs
- **🌐 Cloud-Ready**: Run on Google Colab without local installation
- **📊 Interactive Visualizations**: Rich plots and reports
- **🤖 Smart Automation**: Auto-detection of optimal parameters
- **📚 Educational**: Detailed explanations for learning
- **🔄 Reproducible**: Complete provenance tracking

## ✨ **Key Features**

### **📥 Flexible Data Input**
- Manual file upload (drag & drop)
- Direct download from NCBI SRA/ENA
- API integration for batch processing
- Cloud storage integration (Google Drive, AWS S3)

### **🔬 Comprehensive Analysis**
- **Quality Control**: FastQC, fastp, MultiQC
- **Assembly**: SPAdes, Flye, Unicycler, Canu
- **Annotation**: Prokka, bakta, PGAP, antiSMASH
- **Comparative Genomics**: Pan-genome, phylogeny, ANI
- **Visualization**: Interactive plots, genome browsers

### **🎯 Multiple Use Cases**
- Bacterial/Archaeal genomes
- Fungal genomes
- Plasmid analysis
- Metagenome assembly
- Comparative genomics studies

## 📚 **Pipeline Modules**

| Module | Description | Tools Available |
|--------|-------------|-----------------|
| **🔍 Data Input** | Fetch/upload sequencing data | SRA-tools, wget, manual upload |
| **✅ Quality Control** | Assess and improve read quality | FastQC, fastp, Trimmomatic |
| **🧬 Assembly** | De novo genome assembly | SPAdes, Flye, Unicycler, Canu |
| **📊 Assembly QC** | Evaluate assembly quality | QUAST, BUSCO, CheckM |
| **🏷️ Annotation** | Gene prediction and annotation | Prokka, bakta, PGAP |
| **🔬 Functional Analysis** | Protein function prediction | eggNOG, InterPro, antiSMASH |
| **🌳 Comparative** | Multi-genome comparisons | Roary, fastANI, Mauve |
| **📈 Visualization** | Interactive plots and reports | Plotly, Bokeh, custom plots |

## 🎮 **Usage Examples**

### **Quick Bacterial Assembly**
```python
# Minimal setup for standard bacterial genome
pipeline = GenoFlow()
pipeline.set_mode("bacterial_quick")
pipeline.input_data("SRR12345678")  # SRA accession
pipeline.run_assembly("spades")
pipeline.annotate("prokka")
pipeline.generate_report()
```

### **Comprehensive Analysis**
```python
# Full pipeline with comparative analysis
pipeline = GenoFlow()
pipeline.set_mode("comprehensive")
pipeline.input_data(["genome1.fastq", "genome2.fastq"])
pipeline.run_qc(tools=["fastqc", "fastp"])
pipeline.run_assembly("unicycler", polish=True)
pipeline.annotate(["prokka", "antismash"])
pipeline.comparative_analysis()
pipeline.generate_interactive_report()
```

### **Metagenome Assembly**
```python
# Specialized for metagenomic data
pipeline = GenoFlow()
pipeline.set_mode("metagenome")
pipeline.input_data("metagenome_reads.fastq")
pipeline.run_assembly("metaspades")
pipeline.run_binning("metabat2")
pipeline.taxonomic_classification()
```

## 📁 **Repository Structure**

```
genoflow/
├── 📁 notebooks/
│   ├── GenoFlow_Complete_Pipeline.ipynb    # Main pipeline notebook
│   ├── GenoFlow_Quick_Start.ipynb          # Beginner-friendly version
│   ├── GenoFlow_Advanced.ipynb             # Advanced features
│   └── GenoFlow_Examples/                  # Example analyses
├── 📁 src/
│   ├── genoflow/                           # Core pipeline modules
│   ├── utils/                              # Utility functions
│   └── visualization/                      # Plotting functions
├── 📁 data/
│   ├── examples/                           # Example datasets
│   └── references/                         # Reference databases
├── 📁 docs/
│   ├── user_guide.md                       # Detailed user guide
│   ├── api_reference.md                    # API documentation
│   └── tutorials/                          # Step-by-step tutorials
├── 📁 tests/                               # Unit tests
├── requirements.txt                        # Python dependencies
└── environment.yml                         # Conda environment
```

## 💻 **Installation**

### **Option 1: Google Colab (Recommended for Beginners)**
No installation required! Just click the Colab badge above.

### **Option 2: Local Installation**
```bash
# Clone repository
git clone https://github.com/engkinandatama/genoflow.git
cd genoflow

# Create conda environment
conda env create -f environment.yml
conda activate genoflow

# Install Python packages
pip install -r requirements.txt

# Launch Jupyter
jupyter notebook
```

### **Option 3: Docker**
```bash
docker pull engkinandatama/genoflow:latest
docker run -p 8888:8888 engkinandatama/genoflow:latest
```

## 🔧 **System Requirements**

### **Minimum Requirements**
- Python 3.8+
- 4 GB RAM
- 10 GB free disk space
- Internet connection (for tool downloads)

### **Recommended Specifications**
- 16+ GB RAM
- 100+ GB free disk space
- Multi-core CPU (4+ cores)
- High-speed internet

### **Cloud Computing**
- Google Colab Pro (for large datasets)
- AWS/Azure instances (for production use)

## 📖 **Documentation**

- **📚 [User Guide](docs/user_guide.md)**: Comprehensive usage instructions
- **🔧 [API Reference](docs/api_reference.md)**: Function documentation
- **🎓 [Tutorials](docs/tutorials/)**: Step-by-step learning materials
- **❓ [FAQ](docs/faq.md)**: Frequently asked questions
- **🐛 [Troubleshooting](docs/troubleshooting.md)**: Common issues and solutions

## 🌟 **Example Outputs**

### **Assembly Statistics**
- N50: 2.5 Mbp
- Total length: 4.2 Mbp
- Contigs: 25
- GC content: 42.3%

### **Annotation Results**
- Protein-coding genes: 3,847
- rRNA genes: 12
- tRNA genes: 67
- CRISPR arrays: 2

### **Visualizations**
- Interactive genome browser
- Assembly quality plots
- Phylogenetic trees
- Functional category pie charts

## 🤝 **Contributing**

We welcome contributions! Please see our [Contributing Guidelines](CONTRIBUTING.md).

### **Ways to Contribute**
- 🐛 Report bugs and issues
- 💡 Suggest new features
- 📝 Improve documentation
- 🔧 Add new tools/modules
- 🧪 Contribute example datasets

## 📊 **Performance Benchmarks**

| Dataset Size | Assembly Time | Memory Usage | Colab Compatible |
|-------------|---------------|--------------|------------------|
| Small (< 500MB) | 15-30 min | 2-4 GB | ✅ Yes |
| Medium (500MB-2GB) | 1-3 hours | 4-8 GB | ✅ Yes (Pro) |
| Large (> 2GB) | 3-12 hours | 8-32 GB | ❌ Local/Cloud |

## 🏆 **Citation**

If you use GenoFlow in your research, please cite:

```bibtex
@software{genoflow2025,
  title={GenoFlow: Modular De Novo Genome Assembly and Annotation Pipeline},
  author={Your Name},
  year={2025},
  url={https://github.com/engkinandatama/genoflow},
  version={1.0.0}
}
```

## 📄 **License**

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🙏 **Acknowledgments**

- **Tools Integration**: SPAdes, Prokka, QUAST, and all incorporated tools
- **Communities**: Bioinformatics Stack Exchange, Galaxy Project
- **Funding**: [Your Institution/Grant Information]
- **Contributors**: See [CONTRIBUTORS.md](CONTRIBUTORS.md)

## 📞 **Contact & Support**

- **📧 Email**: your.email@institution.edu
- **🐛 Issues**: [GitHub Issues](https://github.com/engkinandatama/genoflow/issues)
- **💬 Discussions**: [GitHub Discussions](https://github.com/engkinandatama/genoflow/discussions)
- **📱 Twitter**: [@YourTwitter](https://twitter.com/yourtwitter)

## 🔗 **Related Projects**

- [Prokka](https://github.com/tseemann/prokka) - Rapid prokaryotic genome annotation
- [SPAdes](https://github.com/ablab/spades) - Genome assembly toolkit
- [QUAST](https://github.com/ablab/quast) - Quality assessment tool
- [Roary](https://github.com/sanger-pathogens/Roary) - Pan genome pipeline

---

<div align="center">

**🌟 Star this repository if you find it helpful! 🌟**

[![GitHub stars](https://img.shields.io/github/stars/engkinandatama/genoflow.svg?style=social&label=Star)](https://github.com/engkinandatama/genoflow)
[![GitHub forks](https://img.shields.io/github/forks/engkinandatama/genoflow.svg?style=social&label=Fork)](https://github.com/engkinandatama/genoflow/fork)

</div>
