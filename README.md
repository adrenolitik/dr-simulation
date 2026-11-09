# One Diagnosis: Diabetic Retinopathy

A separate version of the “One Diagnosis” project about a single disease. One self-contained `index.html`: no build step, no dependencies, no network.

The interface is bilingual: on the first visit the language is chosen from the browser; the **RU / EN** switch in the top right corner overrides it and the choice is saved. Русское описание: [README.ru.md](README.ru.md).

The main project lives in `../index.html`; this version sits beside it and changes nothing there.

## What it is

A simulation of a person with diabetes who, over time, develops changes in the retina. You choose sex, age at diabetes onset, country, diabetes type and baseline glucose control — then time runs on its own. It stops in five places, and each decision changes sight, money and quality of life.

Unlike the main programme, there is no choice of 16 diseases: everything here is about diabetic retinopathy, its stages, macular oedema and treatment.

## Running it

Open `retinopathy/index.html` in a browser. A local server is optional; if you need one:

```bash
python -m http.server 8000
```

then open `http://localhost:8000/retinopathy/`.

## The five pauses

1. **First changes** — go for tests now, put it off for a year, or “check your sight on the pharmacy chart”.
2. **Tests** — OCT and angiography, OCT only, or refusing to see the whole picture.
3. **Treatment** — depends on the stage: glucose control in NPDR, laser in PDR, anti-VEGF injections for central oedema.
4. **Whom to tell** — family and colleagues, hiding it, or finding a community.
5. **The last stretch** — rehabilitation, continuing treatment, or an experimental therapy.

## What is modelled

- type 1 or type 2 diabetes, age at onset, time until retinopathy appears;
- stages: mild, moderate and severe NPDR, PDR; diabetic macular oedema separately;
- progression under the influence of HbA1c, access to care and treatment;
- loss of vision, vitreous haemorrhage, vitrectomy;
- treatment costs, debt, work, family, rehabilitation;
- four neighbouring lives in other countries with the same diagnosis.

The country setting changes access to screening, laser and injections. It is not decoration: in the model, low access ends in severe sight loss noticeably more often.

## Data

- IDF Diabetes Atlas, 2021 — diabetes prevalence;
- Global Prevalence of Diabetic Retinopathy (Ophthalmology, 2021) — 103.1 million with DR, 28.5 million with vision-threatening DR, 18.8 million with DME in 2020;
- GBD / Vision Loss Expert Group, 2020 — blindness and visual impairment from DR;
- AAO Diabetic Retinopathy Preferred Practice Pattern, 2024 — screening, laser, anti-VEGF;
- UKPDS 35 — the link between HbA1c and microvascular complications.

The figures are rounded and intended as a guide, not as medical advice.

## Limitations

This is a model, not a forecast. It does not account for nephropathy, neuropathy, pregnancy, cataract or other causes of sight loss; it simplifies how likely treatment is to work and how fast the disease progresses. The horizon is the history of the eyes, not lifespan: the simulation ends not with death but with the state of vision.

The simulation is educational: it does not diagnose, prescribe treatment or replace a doctor.

## Controls

- `1`–`3` — choose an answer at a pause;
- `space` — pause;
- `Esc` — leave the simulation;
- settings, language and lived lives are stored only in the browser (`dr.settings.v1`, `dr.lang.v1`, `dr.lives.v1`).

## Licence

MIT, as with the main project.
