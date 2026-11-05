# 🏫 NSW Public Schools: Tableau Data Visualisation

An exploratory visual analysis of **all 2,210 NSW government schools** using Tableau. It examines where schools are located, how student enrolments are distributed, how school types compare, and how socioeconomic advantage (ICSEA) and remoteness relate to school size.


---

## 📌 Project Overview

| | |
|---|---|
| **Goal** | Uncover patterns in school location, school type and enrolment to support evidence-based planning by the NSW Department of Education |
| **Data** | [NSW Government School Locations and Student Enrolment Numbers](https://data.nsw.gov.au/), Data NSW (2,210 schools × 46 columns) |
| **Tool** | Tableau Desktop |
| **Techniques** | Data cleaning in Tableau, geographic roles, binning, box plot, symbol map, treemap, heatmap, bar chart with reference line |

---

## 📂 Repository Structure

```
.
├── NSW_Schools_Visualisation.twbx  
├── data/
│   └── NSW government school locations and student enrolment numbers.csv
├── images/
│   └── NSW Government Schools Analysis Dashboard.png                     
│   ├── Average Student Enrolment by Socioeconomic Band and Remoteness.png
│   ├── Average Student Enrolment by Socioeconomic Advantage (ICSEA) Band.png
│   ├── Distribution of NSW Public Schools by School Type.png
│   ├── Distribution of Student Enrolments by School Type.png
│   └── Geographic Distribution of NSW Public Schools.png
└── README.md
```

---

## 🧹 Data Preparation

- **Missing enrolments:** 41 schools have no `latest_year_enrolment_FTE` because they fall outside the National Schools Statistics Collection. They were excluded from enrolment charts with a NULL filter.
- **Suppressed values:** `Indigenous_pct` and `LBOTE_pct` contain `"np"` (not published) wherever a cohort has 5 or fewer students. These columns were excluded rather than filled with zeros, which would misrepresent those students.
- **Geographic roles:** `Latitude` and `Longitude` were assigned geographic roles so the map renders correctly.
- **Binning:** `ICSEA_value` (about 800–1200) was grouped into **100-point bands** to allow clear socioeconomic comparison.
- **Column selection:** 8 of the 46 columns were kept. These were enrolment, school level, coordinates, ICSEA, remoteness, school name and school code. Contact details and overlapping geographic fields were dropped.

---

## 📊 Visualisations

### 1. Distribution of Student Enrolments by School Type: *Box plot*
![Box plot](images/01_enrolment_boxplot.png)
Secondary schools have the highest median enrolment. Primary schools vary the most in size. Central/Community schools are the smallest. Upper outliers point to high-growth areas of Greater Sydney.

### 2. Geographic Distribution of NSW Public Schools: *Symbol map*
![Map](images/02_school_map.png)
Each school is plotted at its coordinates, coloured by type and sized by enrolment. Schools cluster heavily along the Sydney–Newcastle–Wollongong coast, while western NSW has few, small schools. Central/Community schools appear almost only in rural and remote areas.

### 3. Distribution of Schools by School Type: *Treemap*
![Treemap](images/03_school_type_treemap.png)
Primary schools make up the large majority of government schools, followed by Secondary. Schools for Specific Purposes and Environmental Education Centres are small, specialised segments.

### 4. Average Enrolment by ICSEA Band and Remoteness: *Heatmap*
![Heatmap](images/04_icsea_remoteness_heatmap.png)
Mid-ICSEA (900–1000) schools in Major Cities have the largest average enrolments. Very Remote schools are small in every socioeconomic band.

### 5. Average Enrolment by ICSEA Band: *Bar chart with reference line*
![Bar chart](images/05_icsea_bar_chart.png)
The pattern is an **inverted U**: the 900–1000 band sits above the state average, while both the lowest and highest bands sit below it.

---

## 💡 Key Insights

1. **Location drives school size.** Urban schools are consistently larger than rural and remote schools, mainly because of population density.
2. **There are many small primary schools and fewer, larger secondary schools.** This reflects how the NSW system is structured.
3. **Enrolment does not rise steadily with advantage.** Average school size peaks in mid-range ICSEA schools. Possible reasons are sparse disadvantaged rural communities at the low end and selective schools with capped intake at the high end.
4. **Growth corridors are a planning risk.** Very large outlier schools in Greater Sydney signal pressure on capacity and resources.

**Recommendation:** focus resource and infrastructure planning on remote and low-ICSEA schools, and monitor capacity in high-growth metropolitan corridors.

---

## ⚖️ Ethical Principles Applied

- **Accuracy and honesty:** unmanipulated axes, consistent aggregation, and suppressed values excluded rather than replaced with zeros.
- **Transparency:** every cleaning step and exclusion is documented.
- **Privacy:** analysis stays at aggregate level, with no conclusions drawn about individual schools from suppressed demographic data.

---

---

## 📚 Data Source & Licence

NSW Department of Education, *NSW Government school locations and student enrolment numbers*, via [Data NSW](https://data.nsw.gov.au/). Used under the dataset's open data licence (check the licence on the dataset page).

---

## 👤 Author

**Van Phong Nguyen**
📧 phongnguyenvan97dn@gmail.com
