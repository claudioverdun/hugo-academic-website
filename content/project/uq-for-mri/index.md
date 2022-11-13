---
title: Uncertainty Quantification for Sparse Magnetic Resonance Imaging
summary: An example of using the in-built project page.
tags: []
date: 2022-11-13

# Optional external URL for project (replaces project detail page).
external_link: ''

image:
  caption: Photo by rawpixel on Unsplash
  focal_point: Smart

links: ''
url_code: ''
url_pdf: ''
url_slides: ''
url_video: ''

# Slides (optional).
#   Associate this project with Markdown slides.
#   Simply enter your slide deck's filename without extension.
#   E.g. `slides = "example-slides"` references `content/slides/example-slides.md`.
#   Otherwise, set `slides = ""`.
slides: ""
---

In this project, I worked closely together with the PhD student Frederik Hoppe (RWTH Aachen) as part of our SPARSE3D+ project.
The initial part of this work was made jointly also with Prof. Felix Krahmer (TUM), Prof. Marion Menzel (GE) and Holger Rauhut
(RWTH Aachen). In high-dimensional inverse problems, the estimators are non-linear and given as solutions of optimization problems.
And given a certain noise distribution, the goal is to characterize the probability distribution of the parameter estimates. This is
particularly important in application in safety-critical fields such as self-driving cars, aviation or medical imaging.

Even though many researchers are interested in performing uncertainty quantification (UQ) for deep neural networks, since they provide state-of-the-art
results for many real-world applications (Gawlikowski et al. ’22), even for simpler high-dimensional inverse problems, this is a very
challenging issue and very few methods have been proposed. There is still no unified UQ theory for high-dimensional data problems.

In the case of sparse regression, i.e., when we must retrieve the s-sparse vector {{< math >}}$ \beta_0 \in \mathbb{R}^N ${{< math >}}
from {{< math >}}$ y = X \beta_0 + \varepsilon \in \mathbb{R}^m ${{< math >}} measurements, where {{< math >}}$ m ≪ N ${{< math >}},
and the solution of the high-dimensional inverse problem is obtained via the LASSO (Tibshirani ’96), confidence intervals and hypothesis testing can be obtained
based on the KKT conditions of this convex formulation. This technique was named de-sparsified
LASSO (Zhang & Zhang ’14). Initial works on this method focused on real (sub-)Gaussian measurement
matrices as a toy model. However, in medical imaging applications, such as in MRI inverse problems, the
measurement systems possess physical constraints that translate into structured sensing matrices. From
the mathematical point of view, several independence assumptions are made, e.g., between X ˆΣ−1ei and
X−i, where ˆΣ = X∗X/n is the empirical covariance of the measurement operator X ∈ Rm×N , ei is the
canonical basis vector and X−i represents the the matrix X with the jth column replaced by a column
consisting of zeros. Such strong assumptions do not hold for heavy-tailed random matrices such as those
generated from bounded orthonormal systems and, in particular, randomly subsampled Fourier matrices.

Our contribution was to extended the theory to bounded orthonormal systems, which includes subsampled
Fourier matrices as a particular case. This allows us to construct valid confidence intervals, in a rigorous
way, for the reconstruction of sparse MRI applications that can be described by Fourier operators. This is, up to my knowledge, the
first instance of frequentist uncertainty quantification for high-dimensional MRI problems. This new extension of UQ together with
its applicability to sparse MRI problems, is currently under review for the ICASSP 2023, and a journal version is in preparation.