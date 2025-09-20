---
layout: page
title: Artificial Intelligence Models for Energy Optimization
description: My Bachelor Thesis (TFG) for the Computer Science
img: assets/img/thesis-computer-science/cover.png
importance: 2
category: academics
---

  <p style="text-align: center; font-style: italic;">
  📄 <a href="/assets/pdf/Garcia_Delgado_Juan_Manuel_Grado_en_Ingenieria_Informatica.pdf" target="_blank">
  Download the full thesis (PDF)
  </a>
  </p>

---

## About this work

This page presents my **Bachelor Thesis (Trabajo de Fin de Grado)** for the **Computer Engineering degree** at the [Universidad de Málaga](https://www.uma.es), Spain.  
The thesis, written in Spanish, is titled:

> **“Implementación de Modelos de Inteligencia Artificial para Optimizar el Autoconsumo Energético y Minimizar Vertidos a la Red”**

t received a final grade of _10/10_ and was awarded _Matrícula de Honor_ (highest distinction). It was defended in July 2024 and developed under the supervision of José del Campo Ávila and Rafael Morales Bueno at the Departamento de Lenguajes y Ciencias de la Computación.

The primary goal of this work is the development and implementation of optimization models that dynamically calculate energy distribution coefficients in shared photovoltaic systems. These models aim to **minimize energy injection into the grid** (grid waste) and **improve self-consumption efficiency** in compliance with the Spanish Royal Decree 244/2019.

The complete thesis is structured as follows:

- **Chapter 1: Introduction**  
  Motivation, objectives, methodology (CRISP-DM), structure of the project, and technologies used.

- **Chapter 2: Optimization Methods**  
  Overview of optimization problems and methods: gradient-based algorithms (Gradient Descent, Newton, Quasi-Newton, SLSQP) and gradient-free methods (genetic algorithms).

- **Chapter 3: Data Understanding and Preprocessing**  
  Collection and cleaning of real energy consumption data from Irish users (2009 dataset), transformations for modeling, and integration with photovoltaic generation and energy prices.

- **Chapter 4: Modeling – Minimization of Grid Injection**  
  Formulation of the optimization problem, static vs. dynamic distribution coefficients, constraints, bounds, and implementation of solvers (SLSQP and a custom approximation method).

- **Chapter 5: Evaluation**  
  Performance assessment of the models, stability tests, Wilcoxon test results, and comparative analysis with different user profiles and pricing variables.

- **Chapter 6: Conclusions and Future Work**  
  Summary of findings, practical implications for shared self-consumption, and directions for further research.

---

## Introduction

With the publication of **Royal Decree 244/2019**, new regulatory conditions were defined for photovoltaic self-consumption in Spain. Among the most relevant changes are:  
- Elimination of the so-called “sun tax.”  
- Simplification of administrative procedures.  
- Removal of power installation limits.  
- Recognition of the right to **collective self-consumption**.  

This work is mainly inspired by the last point.  
In collective photovoltaic installations, the energy produced is usually distributed among users using fixed coefficients, regardless of individual consumption patterns. This often leads to significant amounts of energy being injected back into the grid at a much lower price than the purchase cost.  

To address this inefficiency, we explore **artificial intelligence and optimization techniques** to design **dynamic coefficients** that adapt energy allocation in real time to consumption needs. This results in both **economic savings** and **improved energy sustainability**.

---

## Motivation

Traditional static distribution models fail to capture the variability of user consumption patterns, resulting in excessive grid waste.  
By integrating optimization techniques such as **SLSQP (Sequential Least Squares Programming)** and custom approximation algorithms, it is possible to dynamically adjust coefficients and minimize these inefficiencies.  

Moreover, incorporating **real energy price variations** into the optimization model opens the door to not only reducing grid waste but also **maximizing economic benefits** for users in collective self-consumption communities.

---

## Academics

- **Degree:** Computer Engineering (specialization in Computing)  
- **Institution:** [Universidad de Málaga](https://www.uma.es)  
- **Year:** 2024  
- **Department:** Lenguajes y Ciencias de la Computación  
- **Area:** Artificial Intelligence & Optimization  
- **Type:** Applied Research  
- **Modality:** Individual  
- **Pages (main content):** 70  
- **Author:** Juan Manuel García Delgado  
- **Supervisors:** José del Campo Ávila, Rafael Morales Bueno  
