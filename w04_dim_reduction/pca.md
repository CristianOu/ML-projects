# PCA Algorithm - How to
Consider this a helpful reminder of how to implement the PCA from scratch step-by-step. The notation in this description is supposed to match the material from this week.

Given: data points $\mathbf{x}_n \in\mathbb{R}^{D}$, $n=1,\ldots,N$.
<ol>
  <li> Compute sample mean $\overline{\mathbf{x}}=\frac{1}{N}\sum\limits_{n=1}^N \mathbf{x}_n$. 
  <li> Compute sample covariance matrix $\mathbf{S}=\frac{1}{N-1}\sum\limits_{n=1}^N (\mathbf{x}_n-\overline{\mathbf{x}})(\mathbf{x}_n-\overline{\mathbf{x}})^T$.
    Please note that you may find descriptions with a different factor $\frac{1}{N}$ vs. $\frac{1}{N-1}$, and other variants of PCA using the correlation matrix instead of covariance matrix. </li>
  <li> Compute eigenvalues and eigenvectors $\mathbf{S}\mathbf{u_i}=\lambda_i\mathbf{u_i}$, $i=1,\ldots,M$, $\mathbf{S}\in\mathbb{R}^{D\times D}$, $\mathbf{u}_i\in\mathbb{R}^D$.</li>
  <li> Reorder eigenvalues in decreasing order, i.e. $\lambda_i\geq \lambda_j$, $i>j$, and their eigenvectors correspondingly. </li>
  <li> Choose number of components $M < D$ as desired. Put the corresponding $M$ largest eigenvectors $\mathbf{u_i}$ in decreasing order (by eigenlvaue) into the matrix $\mathbf{U}=[\mathbf{u}_1,\ldots,\mathbf{u}_M]^T\in\mathbb{R}^{M \times D}$, i.e. such that $\mathbf{u}_1$ is the eigenvector corresponding to the largest eigenvalue. </li>
  <li> <b>How to feature extraction aka dimensionality reduction</b> from $\mathbf{x}\in\mathbb{R}^D$ to $\mathbf{z}\in\mathbb{R}^M$, $M < D$
    	$$\mathbb{R}^{M} \ni \mathbf{z}_n = \mathbf{U}\left( \mathbf{x}_n-\overline{\mathbf{x}}\right). $$</li>
  <li> <b>How to create a new data point</b> $\mathbf{x}$. Choose (and vary) $\alpha_i$ between $-3\sqrt{\lambda_i} \leq \alpha_i \leq 3\sqrt{\lambda_i}$, to obtain
        $$\mathbb{R}^{D} \ni \mathbf{x} = \overline{\mathbf{x}}+\sum_{i=1}^M \alpha_i \mathbf{u}_i .$$</li>
</ol>
