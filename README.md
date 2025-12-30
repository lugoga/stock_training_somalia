# Somali Fish Stock Training Program

![License](https://img.shields.io/badge/License-CC%20BY%204.0-blue)
![Status](https://img.shields.io/badge/Status-Active-brightgreen)
![Version](https://img.shields.io/badge/Version-1.0-blue)

## Overview

A comprehensive 7-module training program for evidence-based fisheries management in Somalia, developed in partnership with the **Tanzania Fisheries Research Institute (TAFIRI)**.

This repository hosts all training materials, presentations, code examples, and resources for building sustainable fisheries monitoring systems across Somalia's 6 coastal regions.

## 📚 Modules

| Module | Title | Focus | Status |
|--------|-------|-------|--------|
| 1 | Stock Assessment Fundamentals | Concepts & Principles | ✅ Complete |
| 2 | Data Collection Protocols | Sampling & QC | ✅ Complete |
| 3 | Data-Limited Methods | Length-Based Indicators | ✅ Complete |
| 4 | Data Processing & Storage | Cleaning & Database | ✅ Complete |
| 5 | Data Analysis Methods | Statistics & Visualization | ✅ Complete |
| 6 | Practical Field Exercises | Hands-On Training | ✅ Complete |
| 7 | Strategy Development | Regional Coordination | ✅ Complete |

## 🎯 Quick Links

- **[View Training Website](https://somaliafisheries.github.io)** - Quarto website with all 7 modules
- **[Contact & Registration Form](contact.qmd)** - Register for training or get in touch
- **[Full Schedule](docs/schedule.qmd)** - Complete 14-day program timeline (6-24 December 2025)
- **[GitHub Repository](https://github.com/somaliafisheries/training-program)** - Source code
- **[All Presentations](presentations/)** - RevealJS slide decks
- **[Training Manuals](materials/)** - Detailed guides
- **[R Scripts](scripts/)** - Analysis examples
- **[Data Templates](forms/)** - Standardized forms
- **[Implementation Guide](documents/implementation_roadmap.pdf)** - 3-year plan

## 🚀 Getting Started

### For Participants
1. Browse the [Quarto website](https://somaliafisheries.github.io) to view all modules
2. Use the **tabbed navigation** to explore each of the 7 modules
3. Download materials for your region from the Resources menu
4. Review presentations and training manuals
5. Complete practical exercises
6. Contact your regional coordinator

### For Building the Website Locally
```bash
# Clone the repository
git clone https://github.com/somaliafisheries/training-program.git
cd training-program

# Install Quarto (if not already installed)
# Download from: https://quarto.org/docs/get-started/

# Render the website
quarto render

# Preview locally
quarto preview
```

## 📋 Contents

```
.
├── index.html                 # Main website with tabbed interface
├── presentations/             # RevealJS slide decks (7 modules)
├── materials/                 # Training manuals and guides
├── scripts/                   # R analysis examples
├── forms/                     # Data collection templates
├── documents/                 # Implementation guides
├── data/                      # Example datasets
└── README.md                  # This file
```

## 🎓 Learning Outcomes

Participants completing all 7 modules receive a **Certificate of Competency** in:
- Fisheries Stock Assessment
- Data Collection & Management
- Regional Coordination
- Evidence-Based Fisheries Management

**Qualified to:**
- Lead monitoring programs
- Manage fisheries data systems
- Conduct stock assessments
- Advise on management policies
- Train other staff members

## 📊 Key Features

### Evidence-Based
All 7 modules grounded in fisheries science best practices and international standards

### Practical Application
From theory to implementation with hands-on field exercises and real data analysis

### Regional Coordination
Integrated approach across 6 regions with standardized protocols and central database

### Policy Integration
Direct linkages between data and management decisions with policy workshops

### Sustainability Focus
Three-year capacity building plan with training cascade and diverse funding mechanisms

### International Support
TAFIRI partnership provides mentoring, training, and long-term support

## 🌐 Regional Hubs

Training implemented across 6 regions:
1. **Berbera** - Northern commercial hub
2. **Borama** - Northwest
3. **Mogadishu** - Central urban center
4. **Kismayo** - Southern fishing port
5. **Baidoa** - Inland
6. **Galkacyo** - Northeast

## 📈 Implementation Timeline

- **2024:** Complete training & establish national committee
- **2025:** Train technicians & launch monitoring
- **2026:** Accelerate policy integration
- **2027+:** Sustainability & scaling

## 🤝 Partners

- **TAFIRI** - Tanzania Fisheries Research Institute
- **Somalia Fisheries Ministry**
- **Regional Authorities**
- **International Partners**

## 💾 Technology Stack

- **Presentations:** RevealJS (HTML/CSS/JS)
- **Website:** Bootstrap 5
- **Analysis:** R, tidyverse, ggplot2
- **Data Management:** PostgreSQL, SQLite
- **Version Control:** Git/GitHub
- **Hosting:** GitHub Pages

## 📝 License

This work is licensed under the [Creative Commons Attribution 4.0 International License](LICENSE).

You are free to:
- Share and adapt the materials
- Use for training and education
- Modify for your context

With attribution to the original developers.

## 🔗 Resources

### External References
- [FAO Fisheries Resources](https://www.fao.org/fishery/)
- [R for Data Science](https://r4ds.had.co.nz/)
- [IOTC - Indian Ocean Tuna Commission](https://www.iotc.org/)
- [TropFishR R Package](https://github.com/tokami/TropFishR)

### Recommended Reading
- Costello et al. (2012) - Status and Solutions for the World's Unassessed Fisheries
- Froese & Pauly - FishBase
- Hordyk et al. - Length-Based Bayesian Analysis

## 📞 Support

### For Questions & Support
- **Contact Form:** Use our [online registration form](contact.qmd) to get in touch or register for training
- **Email:** [contact@tafiri.go.tz](mailto:contact@tafiri.go.tz)
- **GitHub Issues:** [Report bugs or request features](https://github.com/somaliafisheries/training-program/issues)
- **Discussions:** [Join community discussions](https://github.com/somaliafisheries/training-program/discussions)

### Available Support
- Quarterly video consultations
- Annual in-person visits
- Email technical support
- Peer networking opportunities
- Advanced training on demand
- Joint research collaborations
- Publication support

### Serverless Form Setup
The website includes a contact/registration form using Web3Forms (a free serverless form API). To configure:
1. See [SERVERLESS_FORM_SETUP.md](SERVERLESS_FORM_SETUP.md) for detailed setup instructions
2. Get your free access key from [Web3Forms](https://web3forms.com)
3. Update the access key in `contact.qmd`

## 🤖 Contributing

We welcome contributions! Please:

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/your-improvement`)
3. Commit your changes (`git commit -am 'Add improvement'`)
4. Push to the branch (`git push origin feature/your-improvement`)
5. Create a Pull Request

## 📊 Metrics & Impact

**By 2027, Somalia will have:**
- ✓ Coordinated monitoring at all 6 regions
- ✓ Standardized data collection protocols
- ✓ Real-time data sharing system
- ✓ Monthly regional assessments
- ✓ Quarterly national reports
- ✓ Active policy integration
- ✓ 30+ trained analysts
- ✓ Sustainable funding mechanism

## 🎬 Getting Involved

### If You're a Trainer
- Customize materials for your context
- Use presentations for live training
- Share your implementation experiences
- Contribute improved materials

### If You're a Participant
- Complete all 7 modules
- Engage with your regional coordinator
- Participate in field exercises
- Join the professional network

### If You're a Developer
- Improve the website
- Enhance R scripts
- Build new analysis tools
- Create visualizations

### If You're a Supporter
- Contribute funding for regional programs
- Provide technical expertise
- Offer mentoring support
- Share your experience

## 📜 Citation

If you use these materials, please cite:

```
Somali Fish Stock Training Program (2024). Evidence-Based Fisheries 
Management Training for Sustainable Development. Developed in partnership 
with Tanzania Fisheries Research Institute (TAFIRI). 
Available at: https://github.com/somaliafisheries/training-program
```

## 🙏 Acknowledgments

This program was developed with support from:
- TAFIRI (Tanzania Fisheries Research Institute)
- Somalia Fisheries Ministry
- Regional Fisheries Authorities
- International Conservation Partners
- Fishing Communities

Special thanks to all participants, trainers, and contributors who made this possible.

## 📅 Training Schedule

**Program Dates:** 6-24 December 2025

| Phase | Dates | Content |
|-------|-------|---------|
| Pre-Training | 6 Dec | Training Needs Assessment |
| Opening | 12-13 Dec | Coordination meeting & ceremony |
| **Core Modules** | 14-20 Dec | Modules 1-7 training |
| **Practical** | 21-23 Dec | Research vessel exercises |
| **Graduation** | 24 Dec | Closing ceremony & certificates |

[View Full Schedule](docs/schedule.qmd)

## 🌍 Vision 2027

A unified, evidence-based fisheries management system across Somalia:

> "By 2027, Somalia will have coordinated monitoring at all 6 regions, 
> standardized protocols, real-time data sharing, monthly assessments, 
> and demonstrated policy integration - supporting sustainable fisheries 
> and food security for the Somali people."

---

**Last Updated:** January 2025

**Maintained By:** Somali Fisheries Training Program Team

**Status:** Active Development

*Building sustainable evidence-based fisheries management in Somalia*
