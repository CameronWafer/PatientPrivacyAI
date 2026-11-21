### data by hospital

| hospital | source rows | retained | removed | train (pos/neg) | test (pos/neg) | train prevalence | chol = 0 (retained) |
|---|---|---|---|---|---|---|---|
| Cleveland | 303 | 303 | 0 | 199 (91/108) | 104 (48/56) | 0.46 | 0 |
| Hungary | 294 | 261 | 33 | 172 (65/107) | 89 (33/56) | 0.38 | 0 |
| Switzerland | 123 | 46 | 77 | 30 (30/0) | 16 (15/1) | 1.00 | 46 |
| VA Long Beach | 200 | 130 | 70 | 85 (66/19) | 45 (35/10) | 0.78 | 33 |

### main results (mean ± sd over 5 seeds, BA is balanced accuracy, CH is Switzerland)

| setting | macro BA | worst-hospital BA | worst hospital | worst BA excl. CH | macro accuracy | macro AUROC | pooled test acc. |
|---|---|---|---|---|---|---|---|
| pooled, nonprivate | 0.779 ± 0.005 | 0.650 ± 0.000 | VA Long Beach | 0.650 ± 0.000 | 0.804 ± 0.003 | 0.834 ± 0.001 | 0.794 ± 0.005 |
| local, nonprivate | 0.619 ± 0.014 | 0.486 ± 0.010 | VA Long Beach | 0.487 ± 0.013 | 0.802 ± 0.006 | 0.782 ± 0.002 | 0.771 ± 0.009 |
| local, eps=8 | 0.623 ± 0.010 | 0.486 ± 0.000 | VA Long Beach | 0.486 ± 0.000 | 0.804 ± 0.006 | 0.711 ± 0.096 | 0.772 ± 0.010 |
| local, eps=4 | 0.613 ± 0.017 | 0.474 ± 0.026 | VA Long Beach | 0.489 ± 0.051 | 0.793 ± 0.015 | 0.635 ± 0.083 | 0.764 ± 0.010 |
| local, eps=2 | 0.624 ± 0.010 | 0.467 ± 0.030 | VA Long Beach | 0.489 ± 0.059 | 0.796 ± 0.015 | 0.656 ± 0.128 | 0.768 ± 0.011 |
| local, eps=1 | 0.659 ± 0.068 | 0.477 ± 0.066 | Switzerland | 0.523 ± 0.056 | 0.771 ± 0.032 | 0.701 ± 0.084 | 0.750 ± 0.021 |
| fedavg, nonprivate | 0.780 ± 0.005 | 0.647 ± 0.006 | VA Long Beach | 0.647 ± 0.006 | 0.805 ± 0.004 | 0.834 ± 0.002 | 0.796 ± 0.006 |
| fedavg, clip_only | 0.785 ± 0.002 | 0.650 ± 0.000 | VA Long Beach | 0.650 ± 0.000 | 0.807 ± 0.002 | 0.833 ± 0.001 | 0.799 ± 0.003 |
| fedavg, eps=8 | 0.779 ± 0.007 | 0.647 ± 0.006 | VA Long Beach | 0.647 ± 0.006 | 0.802 ± 0.010 | 0.832 ± 0.002 | 0.788 ± 0.008 |
| fedavg, eps=4 | 0.778 ± 0.005 | 0.637 ± 0.022 | VA Long Beach | 0.637 ± 0.022 | 0.804 ± 0.005 | 0.837 ± 0.003 | 0.791 ± 0.005 |
| fedavg, eps=2 | 0.764 ± 0.012 | 0.624 ± 0.030 | VA Long Beach | 0.624 ± 0.030 | 0.786 ± 0.015 | 0.832 ± 0.013 | 0.779 ± 0.008 |
| fedavg, eps=1 | 0.751 ± 0.015 | 0.601 ± 0.039 | VA Long Beach | 0.601 ± 0.039 | 0.781 ± 0.025 | 0.808 ± 0.014 | 0.757 ± 0.023 |
| mrmtl, nonprivate, lam=0.1 | 0.659 ± 0.005 | 0.500 ± 0.000 | Switzerland | 0.594 ± 0.008 | 0.826 ± 0.009 | 0.832 ± 0.002 | 0.794 ± 0.011 |
| mrmtl, eps=8, lam=0.1 | 0.673 ± 0.007 | 0.500 ± 0.000 | Switzerland | 0.617 ± 0.038 | 0.834 ± 0.004 | 0.835 ± 0.012 | 0.804 ± 0.006 |
| mrmtl, eps=4, lam=0.1 | 0.679 ± 0.061 | 0.500 ± 0.062 | Switzerland | 0.594 ± 0.013 | 0.816 ± 0.020 | 0.830 ± 0.013 | 0.791 ± 0.015 |
| mrmtl, eps=2, lam=0.1 | 0.695 ± 0.051 | 0.522 ± 0.069 | Switzerland | 0.646 ± 0.040 | 0.813 ± 0.020 | 0.828 ± 0.014 | 0.783 ± 0.021 |
| mrmtl, eps=1, lam=0.1 | 0.653 ± 0.036 | 0.519 ± 0.046 | Switzerland | 0.556 ± 0.046 | 0.778 ± 0.043 | 0.796 ± 0.020 | 0.749 ± 0.026 |

### per-hospital balanced accuracy (mean ± sd, 5 seeds)

| setting | Cleveland | Hungary | Switzerland | VA Long Beach |
|---|---|---|---|---|
| pooled, nonprivate | 0.793 ± 0.009 | 0.775 ± 0.013 | 0.900 ± 0.000 | 0.650 ± 0.000 |
| local, nonprivate | 0.773 ± 0.016 | 0.716 ± 0.029 | 0.500 ± 0.000 | 0.487 ± 0.013 |
| local, eps=8 | 0.764 ± 0.026 | 0.744 ± 0.023 | 0.500 ± 0.000 | 0.486 ± 0.000 |
| local, eps=4 | 0.762 ± 0.019 | 0.709 ± 0.031 | 0.493 ± 0.015 | 0.489 ± 0.051 |
| local, eps=2 | 0.759 ± 0.025 | 0.750 ± 0.028 | 0.500 ± 0.000 | 0.489 ± 0.059 |
| local, eps=1 | 0.739 ± 0.016 | 0.728 ± 0.033 | 0.647 ± 0.279 | 0.523 ± 0.056 |
| fedavg, nonprivate | 0.797 ± 0.009 | 0.777 ± 0.014 | 0.900 ± 0.000 | 0.647 ± 0.006 |
| fedavg, clip_only | 0.801 ± 0.005 | 0.789 ± 0.008 | 0.900 ± 0.000 | 0.650 ± 0.000 |
| fedavg, eps=8 | 0.781 ± 0.008 | 0.782 ± 0.016 | 0.907 ± 0.015 | 0.647 ± 0.006 |
| fedavg, eps=4 | 0.791 ± 0.009 | 0.777 ± 0.014 | 0.907 ± 0.015 | 0.637 ± 0.022 |
| fedavg, eps=2 | 0.776 ± 0.026 | 0.765 ± 0.017 | 0.893 ± 0.028 | 0.624 ± 0.030 |
| fedavg, eps=1 | 0.729 ± 0.046 | 0.752 ± 0.028 | 0.920 ± 0.038 | 0.601 ± 0.039 |
| mrmtl, nonprivate, lam=0.1 | 0.787 ± 0.016 | 0.753 ± 0.015 | 0.500 ± 0.000 | 0.594 ± 0.008 |
| mrmtl, eps=8, lam=0.1 | 0.800 ± 0.012 | 0.775 ± 0.014 | 0.500 ± 0.000 | 0.617 ± 0.038 |
| mrmtl, eps=4, lam=0.1 | 0.784 ± 0.019 | 0.766 ± 0.022 | 0.573 ± 0.222 | 0.594 ± 0.013 |
| mrmtl, eps=2, lam=0.1 | 0.762 ± 0.018 | 0.783 ± 0.029 | 0.587 ± 0.213 | 0.646 ± 0.040 |
| mrmtl, eps=1, lam=0.1 | 0.721 ± 0.046 | 0.771 ± 0.033 | 0.567 ± 0.149 | 0.556 ± 0.046 |

### per-hospital accuracy (mean ± sd, 5 seeds)

| setting | Cleveland | Hungary | Switzerland | VA Long Beach |
|---|---|---|---|---|
| pooled, nonprivate | 0.796 ± 0.008 | 0.764 ± 0.008 | 0.812 ± 0.000 | 0.844 ± 0.000 |
| local, nonprivate | 0.777 ± 0.016 | 0.746 ± 0.010 | 0.938 ± 0.000 | 0.747 ± 0.012 |
| local, eps=8 | 0.767 ± 0.025 | 0.757 ± 0.013 | 0.938 ± 0.000 | 0.756 ± 0.000 |
| local, eps=4 | 0.767 ± 0.017 | 0.744 ± 0.015 | 0.925 ± 0.028 | 0.738 ± 0.040 |
| local, eps=2 | 0.763 ± 0.023 | 0.769 ± 0.020 | 0.938 ± 0.000 | 0.716 ± 0.062 |
| local, eps=1 | 0.740 ± 0.018 | 0.755 ± 0.022 | 0.863 ± 0.081 | 0.724 ± 0.084 |
| fedavg, nonprivate | 0.800 ± 0.008 | 0.766 ± 0.018 | 0.812 ± 0.000 | 0.840 ± 0.010 |
| fedavg, clip_only | 0.804 ± 0.005 | 0.769 ± 0.006 | 0.812 ± 0.000 | 0.844 ± 0.000 |
| fedavg, eps=8 | 0.783 ± 0.009 | 0.762 ± 0.012 | 0.825 ± 0.028 | 0.840 ± 0.010 |
| fedavg, eps=4 | 0.794 ± 0.009 | 0.760 ± 0.010 | 0.825 ± 0.028 | 0.836 ± 0.012 |
| fedavg, eps=2 | 0.779 ± 0.026 | 0.762 ± 0.015 | 0.800 ± 0.052 | 0.804 ± 0.024 |
| fedavg, eps=1 | 0.729 ± 0.050 | 0.755 ± 0.026 | 0.850 ± 0.071 | 0.791 ± 0.020 |
| mrmtl, nonprivate, lam=0.1 | 0.792 ± 0.015 | 0.760 ± 0.017 | 0.938 ± 0.000 | 0.813 ± 0.012 |
| mrmtl, eps=8, lam=0.1 | 0.804 ± 0.011 | 0.769 ± 0.019 | 0.938 ± 0.000 | 0.827 ± 0.010 |
| mrmtl, eps=4, lam=0.1 | 0.787 ± 0.018 | 0.764 ± 0.026 | 0.900 ± 0.056 | 0.813 ± 0.020 |
| mrmtl, eps=2, lam=0.1 | 0.767 ± 0.018 | 0.778 ± 0.031 | 0.925 ± 0.028 | 0.782 ± 0.069 |
| mrmtl, eps=1, lam=0.1 | 0.719 ± 0.046 | 0.762 ± 0.033 | 0.887 ± 0.112 | 0.742 ± 0.066 |

### per-hospital AUROC (mean ± sd, 5 seeds)

| setting | Cleveland | Hungary | Switzerland | VA Long Beach |
|---|---|---|---|---|
| pooled, nonprivate | 0.822 ± 0.001 | 0.861 ± 0.003 | 0.933 ± 0.000 | 0.718 ± 0.003 |
| local, nonprivate | 0.821 ± 0.004 | 0.855 ± 0.002 | 0.867 ± 0.000 | 0.587 ± 0.007 |
| local, eps=8 | 0.818 ± 0.008 | 0.849 ± 0.011 | 0.627 ± 0.361 | 0.551 ± 0.040 |
| local, eps=4 | 0.828 ± 0.012 | 0.844 ± 0.015 | 0.293 ± 0.361 | 0.575 ± 0.066 |
| local, eps=2 | 0.817 ± 0.017 | 0.841 ± 0.012 | 0.453 ± 0.438 | 0.513 ± 0.115 |
| local, eps=1 | 0.784 ± 0.033 | 0.833 ± 0.013 | 0.640 ± 0.293 | 0.546 ± 0.096 |
| fedavg, nonprivate | 0.820 ± 0.002 | 0.862 ± 0.003 | 0.933 ± 0.000 | 0.721 ± 0.007 |
| fedavg, clip_only | 0.824 ± 0.001 | 0.858 ± 0.001 | 0.933 ± 0.000 | 0.717 ± 0.003 |
| fedavg, eps=8 | 0.821 ± 0.005 | 0.857 ± 0.004 | 0.933 ± 0.000 | 0.715 ± 0.008 |
| fedavg, eps=4 | 0.824 ± 0.003 | 0.859 ± 0.006 | 0.933 ± 0.000 | 0.730 ± 0.012 |
| fedavg, eps=2 | 0.818 ± 0.011 | 0.855 ± 0.012 | 0.920 ± 0.056 | 0.736 ± 0.031 |
| fedavg, eps=1 | 0.798 ± 0.024 | 0.838 ± 0.010 | 0.907 ± 0.037 | 0.689 ± 0.042 |
| mrmtl, nonprivate, lam=0.1 | 0.824 ± 0.002 | 0.854 ± 0.005 | 0.933 ± 0.000 | 0.717 ± 0.006 |
| mrmtl, eps=8, lam=0.1 | 0.822 ± 0.003 | 0.859 ± 0.002 | 0.920 ± 0.030 | 0.739 ± 0.026 |
| mrmtl, eps=4, lam=0.1 | 0.821 ± 0.008 | 0.860 ± 0.009 | 0.920 ± 0.030 | 0.719 ± 0.028 |
| mrmtl, eps=2, lam=0.1 | 0.820 ± 0.022 | 0.862 ± 0.013 | 0.893 ± 0.037 | 0.738 ± 0.040 |
| mrmtl, eps=1, lam=0.1 | 0.789 ± 0.030 | 0.836 ± 0.013 | 0.867 ± 0.105 | 0.691 ± 0.033 |

### per-hospital sensitivity (mean ± sd, 5 seeds)

| setting | Cleveland | Hungary | Switzerland | VA Long Beach |
|---|---|---|---|---|
| pooled, nonprivate | 0.746 ± 0.017 | 0.818 ± 0.037 | 0.800 ± 0.000 | 1.000 ± 0.000 |
| local, nonprivate | 0.725 ± 0.023 | 0.600 ± 0.122 | 1.000 ± 0.000 | 0.954 ± 0.026 |
| local, eps=8 | 0.725 ± 0.037 | 0.691 ± 0.106 | 1.000 ± 0.000 | 0.971 ± 0.000 |
| local, eps=4 | 0.700 ± 0.060 | 0.576 ± 0.103 | 0.987 ± 0.030 | 0.937 ± 0.042 |
| local, eps=2 | 0.696 ± 0.064 | 0.679 ± 0.111 | 1.000 ± 0.000 | 0.897 ± 0.072 |
| local, eps=1 | 0.725 ± 0.043 | 0.624 ± 0.082 | 0.893 ± 0.076 | 0.886 ± 0.134 |
| fedavg, nonprivate | 0.754 ± 0.017 | 0.818 ± 0.030 | 0.800 ± 0.000 | 0.994 ± 0.013 |
| fedavg, clip_only | 0.771 ± 0.000 | 0.867 ± 0.017 | 0.800 ± 0.000 | 1.000 ± 0.000 |
| fedavg, eps=8 | 0.758 ± 0.019 | 0.861 ± 0.035 | 0.813 ± 0.030 | 0.994 ± 0.013 |
| fedavg, eps=4 | 0.754 ± 0.017 | 0.842 ± 0.040 | 0.813 ± 0.030 | 0.994 ± 0.013 |
| fedavg, eps=2 | 0.733 ± 0.056 | 0.776 ± 0.051 | 0.787 ± 0.056 | 0.949 ± 0.037 |
| fedavg, eps=1 | 0.733 ± 0.027 | 0.739 ± 0.090 | 0.840 ± 0.076 | 0.943 ± 0.029 |
| mrmtl, nonprivate, lam=0.1 | 0.725 ± 0.037 | 0.727 ± 0.077 | 1.000 ± 0.000 | 0.989 ± 0.016 |
| mrmtl, eps=8, lam=0.1 | 0.746 ± 0.027 | 0.800 ± 0.066 | 1.000 ± 0.000 | 0.994 ± 0.013 |
| mrmtl, eps=4, lam=0.1 | 0.746 ± 0.037 | 0.776 ± 0.085 | 0.947 ± 0.056 | 0.989 ± 0.026 |
| mrmtl, eps=2, lam=0.1 | 0.700 ± 0.043 | 0.806 ± 0.087 | 0.973 ± 0.037 | 0.891 ± 0.136 |
| mrmtl, eps=1, lam=0.1 | 0.738 ± 0.050 | 0.806 ± 0.063 | 0.933 ± 0.149 | 0.891 ± 0.108 |

### per-hospital specificity (mean ± sd, 5 seeds)

| setting | Cleveland | Hungary | Switzerland | VA Long Beach |
|---|---|---|---|---|
| pooled, nonprivate | 0.839 ± 0.000 | 0.732 ± 0.013 | 1.000 ± 0.000 | 0.300 ± 0.000 |
| local, nonprivate | 0.821 ± 0.025 | 0.832 ± 0.068 | 0.000 ± 0.000 | 0.020 ± 0.045 |
| local, eps=8 | 0.804 ± 0.022 | 0.796 ± 0.068 | 0.000 ± 0.000 | 0.000 ± 0.000 |
| local, eps=4 | 0.825 ± 0.034 | 0.843 ± 0.044 | 0.000 ± 0.000 | 0.040 ± 0.089 |
| local, eps=2 | 0.821 ± 0.038 | 0.821 ± 0.071 | 0.000 ± 0.000 | 0.080 ± 0.084 |
| local, eps=1 | 0.754 ± 0.054 | 0.832 ± 0.027 | 0.400 ± 0.548 | 0.160 ± 0.152 |
| fedavg, nonprivate | 0.839 ± 0.000 | 0.736 ± 0.039 | 1.000 ± 0.000 | 0.300 ± 0.000 |
| fedavg, clip_only | 0.832 ± 0.010 | 0.711 ± 0.008 | 1.000 ± 0.000 | 0.300 ± 0.000 |
| fedavg, eps=8 | 0.804 ± 0.025 | 0.704 ± 0.010 | 1.000 ± 0.000 | 0.300 ± 0.000 |
| fedavg, eps=4 | 0.829 ± 0.016 | 0.711 ± 0.020 | 1.000 ± 0.000 | 0.280 ± 0.045 |
| fedavg, eps=2 | 0.818 ± 0.060 | 0.754 ± 0.034 | 1.000 ± 0.000 | 0.300 ± 0.071 |
| fedavg, eps=1 | 0.725 ± 0.094 | 0.764 ± 0.066 | 1.000 ± 0.000 | 0.260 ± 0.089 |
| mrmtl, nonprivate, lam=0.1 | 0.850 ± 0.010 | 0.779 ± 0.064 | 0.000 ± 0.000 | 0.200 ± 0.000 |
| mrmtl, eps=8, lam=0.1 | 0.854 ± 0.008 | 0.750 ± 0.061 | 0.000 ± 0.000 | 0.240 ± 0.089 |
| mrmtl, eps=4, lam=0.1 | 0.821 ± 0.033 | 0.757 ± 0.076 | 0.200 ± 0.447 | 0.200 ± 0.000 |
| mrmtl, eps=2, lam=0.1 | 0.825 ± 0.043 | 0.761 ± 0.075 | 0.200 ± 0.447 | 0.400 ± 0.187 |
| mrmtl, eps=1, lam=0.1 | 0.704 ± 0.048 | 0.736 ± 0.053 | 0.200 ± 0.447 | 0.220 ± 0.130 |

### what privacy cost in balanced accuracy (points lost vs nonprivate, negative means private did better)

| method | privacy | Cleveland | Hungary | Switzerland | VA Long Beach |
|---|---|---|---|---|---|
| fedavg | eps=8 | 1.6 | -0.5 | -0.7 | 0.0 |
| fedavg | eps=4 | 0.5 | 0.0 | -0.7 | 1.0 |
| fedavg | eps=2 | 2.1 | 1.2 | 0.7 | 2.3 |
| fedavg | eps=1 | 6.8 | 2.5 | -2.0 | 4.6 |
| local | eps=8 | 0.9 | -2.8 | 0.0 | 0.1 |
| local | eps=4 | 1.1 | 0.7 | 0.7 | -0.1 |
| local | eps=2 | 1.5 | -3.4 | 0.0 | -0.1 |
| local | eps=1 | 3.4 | -1.2 | -14.7 | -3.6 |
| mrmtl | eps=8 | -1.2 | -2.2 | 0.0 | -2.3 |
| mrmtl | eps=4 | 0.4 | -1.4 | -7.3 | 0.0 |
| mrmtl | eps=2 | 2.5 | -3.0 | -8.7 | -5.1 |
| mrmtl | eps=1 | 6.7 | -1.8 | -6.7 | 3.9 |

### what privacy cost in accuracy (points lost vs nonprivate, negative means private did better)

| method | privacy | Cleveland | Hungary | Switzerland | VA Long Beach |
|---|---|---|---|---|---|
| fedavg | eps=8 | 1.7 | 0.4 | -1.2 | 0.0 |
| fedavg | eps=4 | 0.6 | 0.7 | -1.2 | 0.4 |
| fedavg | eps=2 | 2.1 | 0.4 | 1.2 | 3.6 |
| fedavg | eps=1 | 7.1 | 1.1 | -3.7 | 4.9 |
| local | eps=8 | 1.0 | -1.1 | 0.0 | -0.9 |
| local | eps=4 | 1.0 | 0.2 | 1.2 | 0.9 |
| local | eps=2 | 1.3 | -2.2 | 0.0 | 3.1 |
| local | eps=1 | 3.7 | -0.9 | 7.5 | 2.2 |
| mrmtl | eps=8 | -1.2 | -0.9 | 0.0 | -1.3 |
| mrmtl | eps=4 | 0.6 | -0.4 | 3.7 | 0.0 |
| mrmtl | eps=2 | 2.5 | -1.8 | 1.2 | 3.1 |
| mrmtl | eps=1 | 7.3 | -0.2 | 5.0 | 7.1 |

### privacy ledger for every private run

| epsilon_target | hospital_name | n_train_slots | sample_rate | expected_batch | mean_actual_batch | expected_epochs | clip_norm | noise_multiplier | steps | epsilon_realized_max | delta | n_runs |
|---|---|---|---|---|---|---|---|---|---|---|---|---|
| 1.0 | Cleveland | 199 | 0.0804 | 16.0 | 15.96 | 20.1 | 1.0 | 5.312 | 250 | 0.9984 | 1e-05 | 15 |
| 1.0 | Hungary | 172 | 0.093 | 16.0 | 16.0 | 23.3 | 1.0 | 6.133 | 250 | 0.9948 | 1e-05 | 15 |
| 1.0 | Switzerland | 30 | 0.5333 | 16.0 | 16.0 | 133.3 | 1.0 | 34.375 | 250 | 0.9937 | 1e-05 | 15 |
| 1.0 | VA Long Beach | 85 | 0.1882 | 16.0 | 16.1 | 47.1 | 1.0 | 12.188 | 250 | 0.9976 | 1e-05 | 15 |
| 2.0 | Cleveland | 199 | 0.0804 | 16.0 | 15.97 | 20.1 | 1.0 | 2.93 | 250 | 1.9991 | 1e-05 | 15 |
| 2.0 | Hungary | 172 | 0.093 | 16.0 | 15.97 | 23.3 | 1.0 | 3.35 | 250 | 1.9965 | 1e-05 | 15 |
| 2.0 | Switzerland | 30 | 0.5333 | 16.0 | 15.97 | 133.3 | 1.0 | 18.203 | 250 | 1.9983 | 1e-05 | 15 |
| 2.0 | VA Long Beach | 85 | 0.1882 | 16.0 | 15.95 | 47.1 | 1.0 | 6.543 | 250 | 1.9957 | 1e-05 | 15 |
| 4.0 | Cleveland | 199 | 0.0804 | 16.0 | 15.96 | 20.1 | 1.0 | 1.724 | 250 | 3.9907 | 1e-05 | 15 |
| 4.0 | Hungary | 172 | 0.093 | 16.0 | 15.99 | 23.3 | 1.0 | 1.934 | 250 | 3.9983 | 1e-05 | 15 |
| 4.0 | Switzerland | 30 | 0.5333 | 16.0 | 15.95 | 133.3 | 1.0 | 9.844 | 250 | 3.9943 | 1e-05 | 15 |
| 4.0 | VA Long Beach | 85 | 0.1882 | 16.0 | 16.06 | 47.1 | 1.0 | 3.604 | 250 | 3.9977 | 1e-05 | 15 |
| 8.0 | Cleveland | 199 | 0.0804 | 16.0 | 15.93 | 20.1 | 1.0 | 1.114 | 250 | 7.9969 | 1e-05 | 15 |
| 8.0 | Hungary | 172 | 0.093 | 16.0 | 16.05 | 23.3 | 1.0 | 1.221 | 250 | 7.9984 | 1e-05 | 15 |
| 8.0 | Switzerland | 30 | 0.5333 | 16.0 | 16.07 | 133.3 | 1.0 | 5.454 | 250 | 7.997 | 1e-05 | 15 |
| 8.0 | VA Long Beach | 85 | 0.1882 | 16.0 | 15.93 | 47.1 | 1.0 | 2.086 | 250 | 7.9957 | 1e-05 | 15 |

### how sure we are about the main results (95% intervals from resampling test patients)

| setting | all | excl_switzerland |
|---|---|---|
| pooled, nonprivate | 0.779 [0.730, 0.833] | 0.739 [0.681, 0.799] |
| local, nonprivate | 0.619 [0.589, 0.650] | 0.659 [0.617, 0.700] |
| local, eps=8 | 0.623 [0.595, 0.653] | 0.665 [0.626, 0.703] |
| local, eps=4 | 0.613 [0.584, 0.644] | 0.653 [0.613, 0.693] |
| local, eps=2 | 0.624 [0.595, 0.656] | 0.666 [0.624, 0.705] |
| local, eps=1 | 0.659 [0.626, 0.691] | 0.663 [0.624, 0.704] |
| fedavg, nonprivate | 0.780 [0.732, 0.835] | 0.740 [0.682, 0.800] |
| fedavg, clip_only | 0.785 [0.737, 0.839] | 0.747 [0.689, 0.806] |
| fedavg, eps=8 | 0.779 [0.732, 0.833] | 0.737 [0.679, 0.796] |
| fedavg, eps=4 | 0.778 [0.731, 0.830] | 0.735 [0.679, 0.792] |
| fedavg, eps=2 | 0.764 [0.719, 0.814] | 0.722 [0.669, 0.775] |
| fedavg, eps=1 | 0.751 [0.709, 0.796] | 0.694 [0.644, 0.744] |
| mrmtl, nonprivate, lam=0.1 | 0.659 [0.619, 0.705] | 0.712 [0.660, 0.768] |
| mrmtl, eps=8, lam=0.1 | 0.673 [0.635, 0.718] | 0.731 [0.678, 0.786] |
| mrmtl, eps=4, lam=0.1 | 0.679 [0.641, 0.723] | 0.715 [0.667, 0.769] |
| mrmtl, eps=2, lam=0.1 | 0.695 [0.655, 0.735] | 0.731 [0.680, 0.780] |
| mrmtl, eps=1, lam=0.1 | 0.653 [0.617, 0.694] | 0.682 [0.635, 0.733] |

### head to head differences in balanced accuracy (a minus b, with 95% intervals)

| hospitals | a | b | difference (pp) [95% CI] | share_draws_a_better |
|---|---|---|---|---|
| all | fedavg, nonprivate | local, nonprivate | +16.1 [+11.7, +20.7] | 1.0 |
| all | mrmtl, nonprivate, lam=0.1 | fedavg, nonprivate | -12.2 [-15.7, -8.8] | 0.0 |
| all | mrmtl, nonprivate, lam=0.1 | local, nonprivate | +4.0 [+1.1, +7.5] | 1.0 |
| all | fedavg, eps=1 | local, eps=1 | +9.1 [+5.0, +13.5] | 1.0 |
| all | mrmtl, eps=1, lam=0.1 | fedavg, eps=1 | -9.7 [-12.3, -7.2] | 0.0 |
| all | mrmtl, eps=1, lam=0.1 | local, eps=1 | -0.6 [-4.0, +3.4] | 0.39 |
| all | fedavg, eps=2 | local, eps=2 | +14.0 [+10.2, +17.9] | 1.0 |
| all | mrmtl, eps=2, lam=0.1 | fedavg, eps=2 | -7.0 [-9.2, -4.6] | 0.0 |
| all | mrmtl, eps=2, lam=0.1 | local, eps=2 | +7.0 [+4.2, +10.0] | 1.0 |
| all | fedavg, eps=4 | local, eps=4 | +16.5 [+12.2, +21.0] | 1.0 |
| all | mrmtl, eps=4, lam=0.1 | fedavg, eps=4 | -9.9 [-12.2, -7.4] | 0.0 |
| all | mrmtl, eps=4, lam=0.1 | local, eps=4 | +6.6 [+3.7, +10.1] | 1.0 |
| all | fedavg, eps=8 | local, eps=8 | +15.6 [+11.4, +20.1] | 1.0 |
| all | mrmtl, eps=8, lam=0.1 | fedavg, eps=8 | -10.6 [-14.2, -7.4] | 0.0 |
| all | mrmtl, eps=8, lam=0.1 | local, eps=8 | +5.0 [+2.0, +8.6] | 1.0 |
| all | local, nonprivate | local, eps=1 | -4.0 [-6.4, -1.7] | 0.0 |
| all | fedavg, nonprivate | fedavg, eps=1 | +3.0 [+0.3, +5.7] | 0.98 |
| all | mrmtl, nonprivate, lam=0.1 | mrmtl, eps=1, lam=0.1 | +0.5 [-1.6, +2.8] | 0.67 |
| all | local, nonprivate | local, eps=2 | -0.5 [-2.2, +1.0] | 0.28 |
| all | fedavg, nonprivate | fedavg, eps=2 | +1.6 [-0.3, +3.6] | 0.95 |
| all | mrmtl, nonprivate, lam=0.1 | mrmtl, eps=2, lam=0.1 | -3.6 [-5.6, -1.6] | 0.0 |
| all | local, nonprivate | local, eps=4 | +0.6 [-0.8, +1.9] | 0.81 |
| all | fedavg, nonprivate | fedavg, eps=4 | +0.2 [-0.8, +1.2] | 0.66 |
| all | mrmtl, nonprivate, lam=0.1 | mrmtl, eps=4, lam=0.1 | -2.1 [-3.4, -0.6] | 0.0 |
| all | local, nonprivate | local, eps=8 | -0.4 [-1.6, +0.7] | 0.23 |
| all | fedavg, nonprivate | fedavg, eps=8 | +0.1 [-0.8, +0.9] | 0.59 |
| all | mrmtl, nonprivate, lam=0.1 | mrmtl, eps=8, lam=0.1 | -1.4 [-2.5, -0.5] | 0.0 |
| all | fedavg, nonprivate | fedavg, clip_only | -0.5 [-1.6, +0.4] | 0.17 |
| all | fedavg, clip_only | fedavg, eps=1 | +3.4 [+0.7, +6.3] | 1.0 |
| excl_switzerland | fedavg, nonprivate | local, nonprivate | +8.1 [+3.1, +13.5] | 1.0 |
| excl_switzerland | mrmtl, nonprivate, lam=0.1 | fedavg, nonprivate | -2.9 [-7.0, -0.1] | 0.02 |
| excl_switzerland | mrmtl, nonprivate, lam=0.1 | local, nonprivate | +5.3 [+1.3, +9.6] | 1.0 |
| excl_switzerland | fedavg, eps=1 | local, eps=1 | +3.1 [-2.0, +8.5] | 0.87 |
| excl_switzerland | mrmtl, eps=1, lam=0.1 | fedavg, eps=1 | -1.2 [-4.1, +1.5] | 0.2 |
| excl_switzerland | mrmtl, eps=1, lam=0.1 | local, eps=1 | +1.9 [-2.6, +6.6] | 0.76 |
| excl_switzerland | fedavg, eps=2 | local, eps=2 | +5.6 [+1.4, +9.6] | 1.0 |
| excl_switzerland | mrmtl, eps=2, lam=0.1 | fedavg, eps=2 | +0.9 [-0.6, +2.4] | 0.88 |
| excl_switzerland | mrmtl, eps=2, lam=0.1 | local, eps=2 | +6.5 [+2.6, +10.1] | 1.0 |
| excl_switzerland | fedavg, eps=4 | local, eps=4 | +8.2 [+3.1, +13.2] | 1.0 |
| excl_switzerland | mrmtl, eps=4, lam=0.1 | fedavg, eps=4 | -2.0 [-4.6, -0.0] | 0.02 |
| excl_switzerland | mrmtl, eps=4, lam=0.1 | local, eps=4 | +6.1 [+2.1, +10.1] | 1.0 |
| excl_switzerland | fedavg, eps=8 | local, eps=8 | +7.2 [+2.1, +12.5] | 1.0 |
| excl_switzerland | mrmtl, eps=8, lam=0.1 | fedavg, eps=8 | -0.6 [-4.8, +2.4] | 0.41 |
| excl_switzerland | mrmtl, eps=8, lam=0.1 | local, eps=8 | +6.6 [+2.5, +11.0] | 1.0 |
| excl_switzerland | local, nonprivate | local, eps=1 | -0.5 [-3.3, +2.3] | 0.36 |
| excl_switzerland | fedavg, nonprivate | fedavg, eps=1 | +4.6 [+1.6, +7.6] | 1.0 |
| excl_switzerland | mrmtl, nonprivate, lam=0.1 | mrmtl, eps=1, lam=0.1 | +2.9 [+0.1, +5.8] | 0.98 |
| excl_switzerland | local, nonprivate | local, eps=2 | -0.7 [-3.0, +1.4] | 0.28 |
| excl_switzerland | fedavg, nonprivate | fedavg, eps=2 | +1.9 [-0.6, +4.4] | 0.94 |
| excl_switzerland | mrmtl, nonprivate, lam=0.1 | mrmtl, eps=2, lam=0.1 | -1.9 [-4.8, +0.6] | 0.07 |
| excl_switzerland | local, nonprivate | local, eps=4 | +0.5 [-1.2, +2.2] | 0.74 |
| excl_switzerland | fedavg, nonprivate | fedavg, eps=4 | +0.5 [-0.8, +1.9] | 0.78 |
| excl_switzerland | mrmtl, nonprivate, lam=0.1 | mrmtl, eps=4, lam=0.1 | -0.3 [-1.7, +1.0] | 0.33 |
| excl_switzerland | local, nonprivate | local, eps=8 | -0.6 [-2.2, +0.9] | 0.21 |
| excl_switzerland | fedavg, nonprivate | fedavg, eps=8 | +0.4 [-0.8, +1.5] | 0.73 |
| excl_switzerland | mrmtl, nonprivate, lam=0.1 | mrmtl, eps=8, lam=0.1 | -1.9 [-3.3, -0.6] | 0.0 |
| excl_switzerland | fedavg, nonprivate | fedavg, clip_only | -0.6 [-2.2, +0.6] | 0.18 |
| excl_switzerland | fedavg, clip_only | fedavg, eps=1 | +5.3 [+1.9, +8.5] | 1.0 |

### extra checks (mean ± sd, 5 seeds)

| group | setting | macro BA | worst BA | worst BA excl. CH | macro accuracy | macro AUROC |
|---|---|---|---|---|---|---|
| chol_sensitivity | fedavg, eps=2, chol_missing | 0.760 ± 0.058 | 0.620 ± 0.076 | 0.640 ± 0.042 | 0.819 ± 0.014 | 0.847 ± 0.009 |
| chol_sensitivity | fedavg, nonprivate, chol_missing | 0.785 ± 0.005 | 0.650 ± 0.000 | 0.650 ± 0.000 | 0.818 ± 0.007 | 0.850 ± 0.002 |
| chol_sensitivity | local, eps=2, chol_missing | 0.629 ± 0.036 | 0.453 ± 0.054 | 0.540 ± 0.138 | 0.789 ± 0.026 | 0.622 ± 0.037 |
| chol_sensitivity | local, nonprivate, chol_missing | 0.625 ± 0.011 | 0.474 ± 0.021 | 0.476 ± 0.023 | 0.795 ± 0.009 | 0.761 ± 0.004 |
| chol_sensitivity | mrmtl, eps=2, lam=0.1, chol_missing | 0.694 ± 0.045 | 0.514 ± 0.056 | 0.577 ± 0.038 | 0.801 ± 0.020 | 0.779 ± 0.099 |
| chol_sensitivity | mrmtl, nonprivate, lam=0.1, chol_missing | 0.657 ± 0.007 | 0.500 ± 0.000 | 0.597 ± 0.006 | 0.825 ± 0.005 | 0.833 ± 0.001 |
| core | mrmtl, eps=2, lam=0.1 | 0.695 ± 0.051 | 0.522 ± 0.069 | 0.646 ± 0.040 | 0.813 ± 0.020 | 0.828 ± 0.014 |
| core | mrmtl, eps=8, lam=0.1 | 0.673 ± 0.007 | 0.500 ± 0.000 | 0.617 ± 0.038 | 0.834 ± 0.004 | 0.835 ± 0.012 |
| core | mrmtl, nonprivate, lam=0.1 | 0.659 ± 0.005 | 0.500 ± 0.000 | 0.594 ± 0.008 | 0.826 ± 0.009 | 0.832 ± 0.002 |
| equal_weights | fedavg, eps=2, equal_w | 0.677 ± 0.084 | 0.538 ± 0.089 | 0.606 ± 0.075 | 0.773 ± 0.026 | 0.788 ± 0.048 |
| equal_weights | fedavg, nonprivate, equal_w | 0.773 ± 0.002 | 0.550 ± 0.000 | 0.550 ± 0.000 | 0.820 ± 0.002 | 0.841 ± 0.001 |
| equal_weights | mrmtl, eps=2, lam=0.1, equal_w | 0.657 ± 0.053 | 0.510 ± 0.022 | 0.557 ± 0.030 | 0.794 ± 0.031 | 0.770 ± 0.069 |
| equal_weights | mrmtl, nonprivate, lam=0.1, equal_w | 0.665 ± 0.004 | 0.500 ± 0.000 | 0.600 ± 0.000 | 0.830 ± 0.006 | 0.832 ± 0.001 |
| flamby_parity | fedavg, nonprivate, flamby_center | 0.772 ± 0.009 | 0.694 ± 0.019 | 0.694 ± 0.019 | 0.719 ± 0.011 | 0.839 ± 0.008 |
| flamby_parity | local, nonprivate, flamby_center | 0.633 ± 0.018 | 0.496 ± 0.010 | 0.576 ± 0.066 | 0.784 ± 0.013 | 0.736 ± 0.065 |
| flamby_parity | pooled, nonprivate, flamby_pooled | 0.781 ± 0.012 | 0.647 ± 0.042 | 0.647 ± 0.042 | 0.810 ± 0.010 | 0.862 ± 0.003 |
| lambda_sweep | mrmtl, eps=2, lam=0 | 0.624 ± 0.007 | 0.481 ± 0.028 | 0.519 ± 0.043 | 0.795 ± 0.012 | 0.706 ± 0.103 |
| lambda_sweep | mrmtl, eps=2, lam=0.01 | 0.630 ± 0.021 | 0.470 ± 0.042 | 0.549 ± 0.093 | 0.798 ± 0.020 | 0.681 ± 0.090 |
| lambda_sweep | mrmtl, eps=2, lam=1 | 0.709 ± 0.050 | 0.530 ± 0.059 | 0.630 ± 0.044 | 0.808 ± 0.029 | 0.823 ± 0.025 |
| lambda_sweep | mrmtl, eps=8, lam=0 | 0.632 ± 0.020 | 0.494 ± 0.008 | 0.534 ± 0.075 | 0.805 ± 0.006 | 0.694 ± 0.098 |
| lambda_sweep | mrmtl, eps=8, lam=0.01 | 0.621 ± 0.018 | 0.479 ± 0.037 | 0.509 ± 0.071 | 0.800 ± 0.021 | 0.799 ± 0.022 |
| lambda_sweep | mrmtl, eps=8, lam=1 | 0.785 ± 0.003 | 0.640 ± 0.022 | 0.640 ± 0.022 | 0.820 ± 0.007 | 0.834 ± 0.003 |
| lambda_sweep | mrmtl, nonprivate, lam=0 | 0.621 ± 0.008 | 0.489 ± 0.012 | 0.500 ± 0.027 | 0.801 ± 0.006 | 0.783 ± 0.003 |
| lambda_sweep | mrmtl, nonprivate, lam=0.01 | 0.630 ± 0.010 | 0.491 ± 0.008 | 0.510 ± 0.034 | 0.809 ± 0.006 | 0.800 ± 0.010 |
| lambda_sweep | mrmtl, nonprivate, lam=1 | 0.785 ± 0.009 | 0.640 ± 0.022 | 0.640 ± 0.022 | 0.822 ± 0.009 | 0.833 ± 0.001 |
| size_analysis | fedavg, eps=2, cleveland_frac=0.25 | 0.696 ± 0.083 | 0.558 ± 0.104 | 0.601 ± 0.071 | 0.800 ± 0.013 | 0.825 ± 0.012 |
| size_analysis | fedavg, eps=2, cleveland_frac=0.5 | 0.762 ± 0.007 | 0.599 ± 0.031 | 0.599 ± 0.031 | 0.791 ± 0.013 | 0.822 ± 0.009 |
| size_analysis | fedavg, nonprivate, cleveland_frac=0.25 | 0.773 ± 0.006 | 0.647 ± 0.006 | 0.647 ± 0.006 | 0.799 ± 0.008 | 0.836 ± 0.001 |
| size_analysis | fedavg, nonprivate, cleveland_frac=0.5 | 0.780 ± 0.003 | 0.650 ± 0.000 | 0.650 ± 0.000 | 0.803 ± 0.003 | 0.832 ± 0.001 |
| size_analysis | local, eps=2, cleveland_frac=0.25 | 0.623 ± 0.075 | 0.500 ± 0.083 | 0.537 ± 0.069 | 0.756 ± 0.028 | 0.697 ± 0.041 |
| size_analysis | local, eps=2, cleveland_frac=0.5 | 0.617 ± 0.018 | 0.485 ± 0.021 | 0.531 ± 0.045 | 0.780 ± 0.008 | 0.743 ± 0.089 |
| size_analysis | local, nonprivate, cleveland_frac=0.25 | 0.604 ± 0.016 | 0.486 ± 0.017 | 0.511 ± 0.058 | 0.782 ± 0.009 | 0.772 ± 0.004 |
| size_analysis | local, nonprivate, cleveland_frac=0.5 | 0.636 ± 0.026 | 0.489 ± 0.012 | 0.529 ± 0.080 | 0.809 ± 0.006 | 0.783 ± 0.004 |
| size_analysis | mrmtl, eps=2, lam=0.1, cleveland_frac=0.25 | 0.661 ± 0.051 | 0.527 ± 0.061 | 0.599 ± 0.022 | 0.788 ± 0.014 | 0.730 ± 0.077 |
| size_analysis | mrmtl, eps=2, lam=0.1, cleveland_frac=0.5 | 0.667 ± 0.066 | 0.480 ± 0.077 | 0.584 ± 0.051 | 0.798 ± 0.039 | 0.815 ± 0.034 |
| size_analysis | mrmtl, nonprivate, lam=0.1, cleveland_frac=0.25 | 0.654 ± 0.007 | 0.500 ± 0.000 | 0.589 ± 0.012 | 0.823 ± 0.005 | 0.823 ± 0.002 |
| size_analysis | mrmtl, nonprivate, lam=0.1, cleveland_frac=0.5 | 0.657 ± 0.003 | 0.500 ± 0.000 | 0.589 ± 0.012 | 0.822 ± 0.005 | 0.826 ± 0.002 |

### shrinking Cleveland's training set (other hospitals unchanged)

| setting | cleveland n_train | cleveland BA | cleveland accuracy | cleveland AUROC |
|---|---|---|---|---|
| fedavg, eps=2 | 199 | 0.776 ± 0.026 | 0.779 ± 0.026 | 0.818 ± 0.011 |
| fedavg, eps=2, cleveland_frac=0.25 | 50 | 0.738 ± 0.021 | 0.735 ± 0.026 | 0.806 ± 0.015 |
| fedavg, eps=2, cleveland_frac=0.5 | 100 | 0.751 ± 0.033 | 0.750 ± 0.037 | 0.804 ± 0.022 |
| fedavg, nonprivate | 199 | 0.797 ± 0.009 | 0.800 ± 0.008 | 0.820 ± 0.002 |
| fedavg, nonprivate, cleveland_frac=0.25 | 50 | 0.757 ± 0.019 | 0.760 ± 0.020 | 0.823 ± 0.003 |
| fedavg, nonprivate, cleveland_frac=0.5 | 100 | 0.784 ± 0.000 | 0.788 ± 0.000 | 0.824 ± 0.002 |
| local, eps=2 | 199 | 0.759 ± 0.025 | 0.763 ± 0.023 | 0.817 ± 0.017 |
| local, eps=2, cleveland_frac=0.25 | 50 | 0.634 ± 0.081 | 0.635 ± 0.084 | 0.710 ± 0.089 |
| local, eps=2, cleveland_frac=0.5 | 100 | 0.722 ± 0.052 | 0.725 ± 0.048 | 0.788 ± 0.047 |
| local, nonprivate | 199 | 0.773 ± 0.016 | 0.777 ± 0.016 | 0.821 ± 0.004 |
| local, nonprivate, cleveland_frac=0.25 | 50 | 0.713 ± 0.020 | 0.719 ± 0.022 | 0.784 ± 0.008 |
| local, nonprivate, cleveland_frac=0.5 | 100 | 0.795 ± 0.013 | 0.798 ± 0.014 | 0.824 ± 0.004 |
| mrmtl, eps=2, lam=0.1 | 199 | 0.762 ± 0.018 | 0.767 ± 0.018 | 0.820 ± 0.022 |
| mrmtl, eps=2, lam=0.1, cleveland_frac=0.25 | 50 | 0.688 ± 0.032 | 0.681 ± 0.042 | 0.777 ± 0.039 |
| mrmtl, eps=2, lam=0.1, cleveland_frac=0.5 | 100 | 0.759 ± 0.022 | 0.763 ± 0.021 | 0.811 ± 0.015 |
| mrmtl, nonprivate, lam=0.1 | 199 | 0.787 ± 0.016 | 0.792 ± 0.015 | 0.824 ± 0.002 |
| mrmtl, nonprivate, lam=0.1, cleveland_frac=0.25 | 50 | 0.790 ± 0.020 | 0.794 ± 0.019 | 0.818 ± 0.002 |
| mrmtl, nonprivate, lam=0.1, cleveland_frac=0.5 | 100 | 0.786 ± 0.005 | 0.790 ± 0.004 | 0.823 ± 0.001 |
