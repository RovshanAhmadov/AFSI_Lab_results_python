<img width="1292" height="770" alt="image" src="https://github.com/user-attachments/assets/f8cdb7ac-8fc6-4849-a38e-c5b265104c2b" />#This is my Lab cleaning and visualisation project at the Azerbaijan Food and Safety Institute in Google Colab

import pandas as pd
import matplotlib.pyplot as plt

# Data
questions = [
    "Fors-major halları yaranan zaman müştərinin məlumatlandırılması",
    "Şikayət və təklifləriniz nəzərə alınırmı?",
    "Şikayətlərinizin həlli prosesi sizi qane edirmi?",
    "Analiz çeşidlərimizin yetərliliyi sizi qane edirmi?",
    "AQTİ ilə əlaqə qurmaqda çətinliklər yaranırmı?",
    "Göstərilən xidmətlər barədə ətraflı məlumat verilirmi?",
    "Sınaq nəticələrinin vaxtında təqdim edilirmi?",
    "Xidmət əsnasında gecikmələr yaranıbmı?",
    "Müştəri ilə münasibət və davranışlar sizi qane edirmi?",
    "Müraciət proseslərinin asanlığından razısınızmı?"
]

data = {
    "I rüb": [33.7, 37, 36.9, 38.5, 38.8, 39, 39.2, 38.9, 39.7, 40.2],
    "II rüb": [29.6, 31.7, 31, 32.7, 33.7, 33.7, 32.9, 33.7, 34.1, 34.4],
    "III rüb": [35.8, 38, 38, 41.1, 41.4, 42, 42.4, 33.5, 42.7, 43.2]
}

# Create DataFrame
df = pd.DataFrame(data, index=questions)

# Plot
plt.figure(figsize=(15, 9))

for q in questions:
    plt.plot(df.columns, df.loc[q], marker='o', label=q)

plt.xlabel("Rüblər")
plt.ylabel("Faiz (%)")
plt.title("Müştəri Məmnuniyyəti – Rüblər üzrə müqayisə")
plt.legend(loc="upper left", bbox_to_anchor=(1, 1))
plt.grid(True, linestyle='--', linewidth=0.5, alpha=0.5)
plt.tight_layout()
plt.show()







import pandas as pd
import matplotlib.pyplot as plt

# Data
questions = [
    "Fors-major halları yaranan zaman müştərinin məlumatlandırılması",
    "Şikayət və təklifləriniz nəzərə alınırmı?",
    "Şikayətlərinizin həlli prosesi sizi qane edirmi?",
    "Analiz çeşidlərimizin yetərliliyi sizi qane edirmi?",
    "AQTİ ilə əlaqə qurmaqda çətinliklər yaranırmı?",
    "Göstərilən xidmətlər barədə ətraflı məlumat verilirmi?",
    "Sınaq nəticələrinin vaxtında təqdim edilirmi?",
    "Xidmət əsnasında gecikmələr yaranıbmı?",
    "Müştəri ilə münasibət və davranışlar sizi qane edirmi?",
    "Müraciət proseslərinin asanlığından razısınızmı?"
]

data = {
    "I rüb": [33.7, 37, 36.9, 38.5, 38.8, 39, 39.2, 38.9, 39.7, 40.2],
    "II rüb": [29.6, 31.7, 31, 32.7, 33.7, 33.7, 32.9, 33.7, 34.1, 34.4],
    "III rüb": [35.8, 38, 38, 41.1, 41.4, 42, 42.4, 33.5, 42.7, 43.2]
}

df = pd.DataFrame(data, index=questions)

plt.figure(figsize=(14, 9))

offset_step = 4  # distance between lines (increase for bigger spacing)

for i, q in enumerate(questions):
    offset = i * offset_step
    plt.plot(df.columns, df.loc[q] + offset, marker='o', label=q)

plt.xlabel("Rüblər")
plt.ylabel("Faiz (%) (offset applied)")
plt.title("Müştəri Məmnuniyyəti – Rüblər üzrə genişləndirilmiş xətt aralığı")
plt.legend(loc="upper left", bbox_to_anchor=(1, 1))
plt.grid(True, linestyle='--', alpha=0.4)
plt.tight_layout()
plt.show()

import pandas as pd
import matplotlib.pyplot as plt

# Data
questions = [
    "Fors-major halları yaranan zaman müştərinin məlumatlandırılması",
    "Şikayət və təklifləriniz nəzərə alınırmı?",
    "Şikayətlərinizin həlli prosesi sizi qane edirmi?",
    "Analiz çeşidlərimizin yetərliliyi sizi qane edirmi?",
    "AQTİ ilə əlaqə qurmaqda çətinliklər yaranırmı?",
    "Göstərilən xidmətlər barədə ətraflı məlumat verilirmi?",
    "Sınaq nəticələrinin vaxtında təqdim edilirmi?",
    "Xidmət əsnasında gecikmələr yaranıbmı?",
    "Müştəri ilə münasibət və davranışlar sizi qane edirmi?",
    "Müraciət proseslərinin asanlığından razısınızmı?"
]

data = {
    "I rüb": [33.7, 37, 36.9, 38.5, 38.8, 39, 39.2, 38.9, 39.7, 40.2],
    "II rüb": [29.6, 31.7, 31, 32.7, 33.7, 33.7, 32.9, 33.7, 34.1, 34.4],
    "III rüb": [35.8, 38, 38, 41.1, 41.4, 42, 42.4, 33.5, 42.7, 43.2]
}

df = pd.DataFrame(data, index=questions)

# PowerPoint HD slide size (16:9)
plt.figure(figsize=(16, 9))

offset_step = 6  # vertical spacing between lines

for i, q in enumerate(questions):
    offset = i * offset_step
    plt.plot(df.columns,
             df.loc[q] + offset,
             marker='o',
             linewidth=3,
             markersize=10,
             label=f"{i+1}. {q}")  # numbering for shorter legend

plt.xlabel("Rüblər", fontsize=16)
plt.ylabel("Faiz (%)", fontsize=16)

plt.xticks(fontsize=14)
plt.yticks(fontsize=14)

plt.grid(True, linestyle='--', linewidth=0.6, alpha=0.5)

# Legend on right side, large font
plt.legend(loc="center left", bbox_to_anchor=(1, 0.5), fontsize=12)

plt.tight_layout()
plt.show()

import pandas as pd
import matplotlib.pyplot as plt

# Data
questions = [
    "Fors-major halları yaranan zaman müştərinin məlumatlandırılması",
    "Şikayət və təklifləriniz nəzərə alınırmı?",
    "Şikayətlərinizin həlli prosesi sizi qane edirmi?",
    "Analiz çeşidlərimizin yetərliliyi sizi qane edirmi?",
    "AQTİ ilə əlaqə qurmaqda çətinliklər yaranırmı?",
    "Göstərilən xidmətlər barədə ətraflı məlumat verilirmi?",
    "Sınaq nəticələrinin vaxtında təqdim edilirmi?",
    "Xidmət əsnasında gecikmələr yaranıbmı?",
    "Müştəri ilə münasibət və davranışlar sizi qane edirmi?",
    "Müraciət proseslərinin asanlığından razısınızmı?"
]

data = {
    "I rüb": [33.7, 37, 36.9, 38.5, 38.8, 39, 39.2, 38.9, 39.7, 40.2],
    "II rüb": [29.6, 31.7, 31, 32.7, 33.7, 33.7, 32.9, 33.7, 34.1, 34.4],
    "III rüb": [35.8, 38, 38, 41.1, 41.4, 42, 42.4, 33.5, 42.7, 43.2]
}

df = pd.DataFrame(data, index=questions)

plt.figure(figsize=(16, 9))

offset_step = 6  # vertical spacing between lines

for i, q in enumerate(questions):
    offset = i * offset_step
    plt.plot(df.columns,
             df.loc[q] + offset,
             marker='o',
             linewidth=3,
             markersize=10,
             label=f"{i+1}. {q}")

plt.xlabel("Rüblər", fontsize=18)
plt.ylabel("Faiz (%)  (offset added)", fontsize=18)

plt.xticks(fontsize=16)
plt.yticks(fontsize=16)

plt.grid(True, linestyle='--', linewidth=0.6, alpha=0.5)

# ⭐ Legend fully outside (far left)
plt.legend(
    loc="center left",
    bbox_to_anchor=(-0.45, 0.5),   # move left more
    fontsize=15,
)

plt.tight_layout()
plt.show()

import pandas as pd
import matplotlib.pyplot as plt

# Data
questions = [
    "Fors-major halları yaranan zaman müştərinin məlumatlandırılması",
    "Şikayət və təklifləriniz nəzərə alınırmı?",
    "Şikayətlərinizin həlli prosesi sizi qane edirmi?",
    "Analiz çeşidlərimizin yetərliliyi sizi qane edirmi?",
    "AQTİ ilə əlaqə qurmaqda çətinliklər yaranırmı?",
    "Göstərilən xidmətlər barədə ətraflı məlumat verilirmi?",
    "Sınaq nəticələrinin vaxtında təqdim edilirmi?",
    "Xidmət əsnasında gecikmələr yaranıbmı?",
    "Müştəri ilə münasibət və davranışlar sizi qane edirmi?",
    "Müraciət proseslərinin asanlığından razısınızmı?"
]

data = {
    "I rüb": [33.7, 37, 36.9, 38.5, 38.8, 39, 39.2, 38.9, 39.7, 40.2],
    "II rüb": [29.6, 31.7, 31, 32.7, 33.7, 33.7, 32.9, 33.7, 34.1, 34.4],
    "III rüb": [35.8, 38, 38, 41.1, 41.4, 42, 42.4, 33.5, 42.7, 43.2]
}

df = pd.DataFrame(data, index=questions)

plt.figure(figsize=(16, 10))

offset_step = 6

for i, q in enumerate(questions):
    offset = i * offset_step
    plt.plot(df.columns,
             df.loc[q] + offset,
             marker='o',
             linewidth=3,
             markersize=10,
             label=f"{i+1}. {q}")

plt.xlabel("Rüblər", fontsize=18)
plt.ylabel("Faiz (%)", fontsize=18)
plt.xticks(fontsize=16)
plt.yticks(fontsize=14)

plt.grid(True, linestyle='--', linewidth=0.6, alpha=0.5)

# ⭐ Legend ABOVE the plot in two columns (no overlap guaranteed)
plt.legend(
    loc="lower center",
    bbox_to_anchor=(0.5, 1.15),
    fontsize=14,
    ncol=2,
    frameon=False
)

plt.tight_layout()
plt.show()

import pandas as pd
import matplotlib.pyplot as plt
import numpy as np

# --- Create DataFrame ---
data = {
    "Tabeçilik": [
        "Abşeron RTİ",
        "Bakı Şəhəri üzrə Tİ",
        "Gəncə-Daşkəsən RTİ",
        "Qarabağ RTİ",
        "Mərkəzi Aran RTİ"
    ],
    "Aşağı risk": [0, 7, 0, 0, 0],
    "Orta risk": [3, 223, 28, 38, 27],
    "Yüksək risk": [6, 84, 14, 11, 13]
}

df = pd.DataFrame(data)

# --- Plot ---
labels = df["Tabeçilik"]
x = np.arange(len(labels))
width = 0.25  # bar width

fig, ax = plt.subplots(figsize=(12, 6))

ax.bar(x - width, df["Aşağı risk"], width, label="Aşağı risk")
ax.bar(x, df["Orta risk"], width, label="Orta risk")
ax.bar(x + width, df["Yüksək risk"], width, label="Yüksək risk")

ax.set_xticks(x)
ax.set_xticklabels(labels, rotation=45, ha="right")

ax.set_ylabel("Say")
ax.set_title("Məktəbəqədər təhsil müəssisələrinin risk qrupları")
ax.legend()

plt.tight_layout()
plt.show()

import pandas as pd
import matplotlib.pyplot as plt

# --- DATA ---
data = {
    "Tabeçilik": [
        "Abşeron Regional Təhsil İdarəsi",
        "Bakı Şəhəri üzrə Təhsil İdarəsi",
        "Gəncə-Daşkəsən Regional Təhsil İdarəsi",
        "Qarabağ Regional Təhsil İdarəsi",
        "Mərkəzi Aran Regional Təhsil İdarəsi"
    ],
    "Uyğun deyil %": [11.11, 12.08, 12.5, 12.5, 6.67],
    "Uyğundur %": [88.89, 87.92, 87.5, 87.5, 93.3]
}

df = pd.DataFrame(data)

# --- PLOT ---
plt.figure(figsize=(14, 7), dpi=150)

plt.plot(df["Tabeçilik"], df["Uyğun deyil %"], marker='o', linewidth=3, label="Uyğun deyil %")
plt.plot(df["Tabeçilik"], df["Uyğundur %"], marker='o', linewidth=3, label="Uyğundur %")

plt.xticks(rotation=25, fontsize=12)
plt.yticks(fontsize=12)

plt.xlabel("Tabeçilik", fontsize=14)
plt.ylabel("Faiz (%)", fontsize=14)

plt.grid(True, linestyle="--", alpha=0.5)

plt.legend(loc="upper left", fontsize=13, frameon=True)

plt.tight_layout()
plt.show()

import pandas as pd
import matplotlib.pyplot as plt

# --- DATA ---
df = pd.DataFrame({
    "Tabeçilik": [
        "Abşeron RTİ",
        "Bakı ŞTİ",
        "Gəncə-Daşkəsən RTİ",
        "Qarabağ RTİ",
        "Mərkəzi Aran RTİ"
    ],
    "Uyğun deyil %": [11.11, 12.08, 12.5, 12.5, 6.67],
    "Uyğundur %": [88.89, 87.92, 87.5, 87.5, 93.3]
})

# --- EXCEL STYLE PLOT ---
plt.figure(figsize=(12, 6), dpi=150)

# Excel-style default colors (blue & orange)
plt.plot(df["Tabeçilik"], df["Uyğun deyil %"], marker='o', linewidth=2.5, label="Uyğun deyil %")
plt.plot(df["Tabeçilik"], df["Uyğundur %"], marker='o', linewidth=2.5, label="Uyğundur %")

# Clear Excel-like formatting
plt.grid(True, linestyle="--", alpha=0.4)
plt.xticks(rotation=20, fontsize=12)
plt.yticks(fontsize=12)
plt.xlabel("Tabeçilik", fontsize=13)
plt.ylabel("Faiz (%)", fontsize=13)

# Excel legend style
plt.legend(fontsize=12, frameon=True)

plt.tight_layout()
plt.show()

import pandas as pd
import matplotlib.pyplot as plt
from ipywidgets import widgets, interact

# --- DATA ---
df = pd.DataFrame({
    "Tabeçilik": [
        "Abşeron RTİ",
        "Bakı ŞTİ",
        "Gəncə-Daşkəsən RTİ",
        "Qarabağ RTİ",
        "Mərkəzi Aran RTİ"
    ],
    "Uyğun deyil": [1, 40, 5, 12, 3],
    "Uyğun deyil %": [11.11, 12.08, 12.5, 12.5, 6.67],
    "Uyğundur": [8, 291, 35, 84, 42],
    "Uyğundur %": [88.89, 87.92, 87.5, 87.5, 93.3]
})

# --- INTERACTIVE FILTER FUNCTION ---
def plot_regions(selected_regions):
    plt.figure(figsize=(14, 6), dpi=150)

    filtered = df[df["Tabeçilik"].isin(selected_regions)]

    # Line chart for percentages (Excel-style colors)
    plt.plot(filtered["Tabeçilik"], filtered["Uyğun deyil %"],
             marker='o', linewidth=3, label="Uyğun deyil %")
    plt.plot(filtered["Tabeçilik"], filtered["Uyğundur %"],
             marker='o', linewidth=3, label="Uyğundur %")

    # Add number labels on the chart
    for i, row in filtered.iterrows():
        plt.text(row["Tabeçilik"], row["Uyğun deyil %"],
                 f"{row['Uyğun deyil']} nəfər", fontsize=10, ha='center', va='bottom')
        plt.text(row["Tabeçilik"], row["Uyğundur %"],
                 f"{row['Uyğundur']} nəfər", fontsize=10, ha='center', va='bottom')

    plt.grid(True, linestyle="--", alpha=0.4)
    plt.xticks(rotation=20, fontsize=12)
    plt.yticks(fontsize=12)
    plt.xlabel("Tabeçilik", fontsize=13)
    plt.ylabel("Faiz (%)", fontsize=13)
    plt.legend(fontsize=12)
    plt.tight_layout()
    plt.show()

# --- MULTISELECT FILTER (LIKE EXCEL SLICER) ---
regions = df["Tabeçilik"].tolist()
region_selector = widgets.SelectMultiple(
    options=regions,
    value=tuple(regions),
    description='Region:',
    disabled=False
)

interact(plot_regions, selected_regions=region_selector)

