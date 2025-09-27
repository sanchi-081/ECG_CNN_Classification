# Jetson Nano Deployment Results

The best-performing ResNet model was quantized (INT8 TFLite) and deployed on 
NVIDIA Jetson Nano. Below are the performance metrics:

| Metric                     | Value                         |
|----------------------------|-------------------            |
| Predicted Class            | MI (Myocardial Infarction)    |
| Confidence                 | 99.61 %                       |
| Model Size                 | 0.67 MB                       |
| Preprocessing Time         | 40.84 ms                      |
| Avg. Inference Time        | 606.81 ms (~1.65 FPS)         |
| Avg. CPU Usage             | 8.04 %                        |
| Avg. RAM Usage             | 3035.96 MB / 3963.96 MB       |
| Peak Program Memory Usage  | 10.08 MB                      |
| OS                         | Linux 4.9.299-tegra (aarch64) |
| CPU Cores                  | 4                             |
| Total RAM                  | 3963.96 MB                    |
