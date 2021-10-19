# SLI & SLO containerD Windows

**Azure VM SKU: Standard_D32s_v3**

WS 2019 with HCSSHIM 0.9
Sample size: 1000 pods, sequential
             200 containers, sequential

| Operation         | Fastest Time | Average Time | Slowest Time | Delta average D2s_v3 | 95th %  | 50th % |
| --- | --- | --- | --- | --- | --- | --- |
| create PodSandbox | 1.7573s      | 1.9228s      | 3.4020s      |                      | 2.1040s | 1.8909s |
| stop PodSandbox   | 0.6826s      | 0.7537s      | 1.4773s      |                      | 0.8281s | 0.7391s |   
| remove PodSandbox | 0.130s       | 0.1573s      | 2.062s       |                      | 0.171s  | 0.153s  |
| create Container  | 0.072s       | 0.089s       | 0.160s       |                      | 0.111s  | 0.86s   |
| start  Container  | 1.483s       | 1.566s       | 1.9868       |                      | 1.630s  | 1.588s  |
| status Container  | 0.0001s      | 0.001s       | 0.0097s      |                      | 0.0021s | 0.0008s |
| stop   Container  | 3.048s       | 3.497s       | 5.298s       |                      | 3.539s  | 3.477s  |
| remove Container  | 0.015s       | 0.025s       | 0.041s       |                      | 0.031s  | 0.024s  |

WS 2019 with HCSSHIM 0.8

| Operation         | Fastest Time | Average Time | Slowest Time | Delta average D2s_v3 | 95th %  | 50th % |
| --- | --- | --- | --- | --- | --- | --- |
| create PodSandbox | 2.018s      | 2.135s      | 3.125s      |                      | 2.267s | 2.121s |
| stop PodSandbox   | 0.699s      | 0.760s      | 1.230s      |                      | 0.806s | 0.7512s |   
| remove PodSandbox | 0.134s       | 0.160s      | 0.493s       |                      | 0.176s  | 0.157s  |
| CreateContainer | 0.0680s | 0.0866s | 0.139s | |0.102s | 0.0849s |
| StatusContainer | 0.0s | 0.001s | 0.0079s | | 0.0026s | 0.0008s |
| StopContainer | 3.2067s | 3.4960s | 4.7731s || 3.5588s | 3.4878s |
| RemoveContainer | 0.0102s | 0.0253s | 0.0709s | | 0.0315s | 0.0245s |
| StartContainer | 1.463s | 1.551s | 1.817s | | 1.617s | 1.544s |


*** 

WS 2022 with HCSSHIM 0.9
Sample size: 1000 pods, sequential
             200 containers, sequential
             
| Operation         | Fastest Time | Average Time | Slowest Time | Delta average D2s_v3 | 95th %  | 50th % |
| --- | --- | --- | --- | --- | --- | --- |
| CreatePod | 2.260506s | 2.4084s | 3.972s | | 2.595s | 2.3821s |
| StatusPod | 0.0s | 0.0011s | 0.0033s | | 0.0016s | 0.0011s |
| StopPod | 0.5978s | 0.6827s | 1.338s | | 0.8035s | 0.6698s |
| RemovePod | 0.0974s | 0.1172s | 0.5200s | | 0.127s | 0.116s |
| CreateContainer | 0.0708s | 0.0910s | 0.2973s | | 0.1060s | 0.0856s |
| StatusContainer | 0.0s | 0.00058s | 0.00219s | | 0.0010s | 0.0005s |
| StopContainer | 1.9983s | 2.8090s | 3.1359s | | 2.8953s | 2.8342s |
| RemoveContainer | 0.0178s | 0.0234s | 0.05912s | | 0.02825s | 0.0230s |
| StartContainer | 2.1134s | 2.2484s | 4.0323s | | 2.5372s | 2.2122s |



***
### CREATE POD HCSSHIM 0.9 vs 0.8 ( WS 2019 )  vs WS2022 HCSSHIM 0.9

![CreatePod_WS2019_d32s_v3](https://user-images.githubusercontent.com/7319830/137918655-44aa91fd-bf7c-47bc-93f0-e01e340d59c2.png)
![CreatePod_WS2019_old_hcsshim_d32s_v3](https://user-images.githubusercontent.com/7319830/137918691-7fe3474e-f068-4ec6-8f8a-b738f40ba4bb.png)
![CreatePod_big_sample_d32s_v3](https://user-images.githubusercontent.com/7319830/137918307-195ec30f-eb74-4073-a8a3-0f0f4b691eb7.png)
![CreatePod_WS2022_d32s_v3](https://user-images.githubusercontent.com/7319830/137919251-de439322-dd88-4859-84ca-188e47d71b21.png)

### STOP POD HCSSHIM 0.9 vs 0.8  ( WS 2019 )  vs WS2022 HCSSHIM 0.9

![StopPod_WS2019_d32s_v3](https://user-images.githubusercontent.com/7319830/137918995-7dddeffc-1ea1-4592-bef3-6538401cb6fe.png)
![StopPod_WS2019_old_hcsshim_d32s_v3](https://user-images.githubusercontent.com/7319830/137919000-bf0b670f-bd13-4636-9f29-97bbbe7ff842.png)
![StopPod_big_sample_d32s_v3](https://user-images.githubusercontent.com/7319830/137919010-8ef526a1-1484-4058-b596-85280f3f7c63.png)
![StopPod_WS2022_d32s_v3](https://user-images.githubusercontent.com/7319830/137919210-a3eeb97d-cc38-4c13-be35-7a2a77cd27ac.png)

### REMOVE POD HCSSHIM 0.9 vs 0.8  ( WS 2019 )  vs WS2022 HCSSHIM 0.9

![RemovePod_WS2019_old_hcsshim_d32s_v3](https://user-images.githubusercontent.com/7319830/137919089-cca4cf97-eae5-480c-9787-c0ff939ff9cd.png)
![RemovePod_WS2019_d32s_v3](https://user-images.githubusercontent.com/7319830/137919091-0d9288f3-e722-422a-9f60-41bbcce799dc.png)
![RemovePod_WS2022_d32s_v3](https://user-images.githubusercontent.com/7319830/137919177-4f2f0532-64c2-475b-a2b1-5260936f2b75.png)

### CREATE CONTAINER HCSSHIM 0.9 vs 0.8 ( WS 2019 )  

![CreateContainer_WS2019_ols_hcsshim_d32s_v3](https://user-images.githubusercontent.com/7319830/137919377-438ff348-2dda-4277-9911-d20bdc953d13.png)
![CreateContainer_WS2019_d32s_v3](https://user-images.githubusercontent.com/7319830/137919379-bf0e3cc9-7129-4be4-871a-aaceb92578a8.png)
![CreateContainer_WS2022_d32s_v3](https://user-images.githubusercontent.com/7319830/137923397-b4962b7a-32ac-4133-943d-4ce00dbc534b.png)

### STATUS CONTAINER HCSSHIM  0.9 vs 0.8 ( WS 2019 ) 

![StatusContainer_WS2019_d32s_v3](https://user-images.githubusercontent.com/7319830/137919462-5494b881-b239-4767-a426-9c9919aeb4c2.png)
![StatusContainer_WS2019_ols_hcsshim_d32s_v3](https://user-images.githubusercontent.com/7319830/137919467-8f5987c8-d399-4a75-b731-c3185d9e7173.png)
![StatusContainer_WS2022_d32s_v3](https://user-images.githubusercontent.com/7319830/137923439-45b46fcd-1d08-40f5-b35d-dbe1c6fec207.png)

### START CONTAINER  HCSSHIM  0.9 vs 0.8 ( WS 2019 ) 

![StartContainer_WS2019_ols_hcsshim_d32s_v3](https://user-images.githubusercontent.com/7319830/137919530-2f4dc291-35b7-4447-807a-d9a87721648d.png)
![StartContainer_WS2019_d32s_v3](https://user-images.githubusercontent.com/7319830/137919535-548d7318-59fe-4ca3-98a5-88c7d318af14.png)
![StartContainer_WS2022_d32s_v3](https://user-images.githubusercontent.com/7319830/137923478-93e689f4-d8e4-456a-8c9e-38152567d678.png)

### STOP CONTAINER  HCSSHIM  0.9 vs 0.8 ( WS 2019 ) 

![StopContainer_WS2019_ols_hcsshim_d32s_v3](https://user-images.githubusercontent.com/7319830/137919602-008fb937-1738-4fea-8d65-90c50dda1d80.png)
![StopContainer_WS2019_d32s_v3](https://user-images.githubusercontent.com/7319830/137919606-1c270637-69ba-45a8-8f86-b3ab1bf49b1f.png)
![StopContainer_WS2022_d32s_v3](https://user-images.githubusercontent.com/7319830/137923528-b6d8af63-3d0f-4e7e-a085-03df51b7bad2.png)

### REMOVE CONTAINER  HCSSHIM  0.9 vs 0.8 ( WS 2019 ) 

![RemoveContainer_WS2019_ols_hcsshim_d32s_v3](https://user-images.githubusercontent.com/7319830/137919670-b0bf7071-fc36-4670-969d-0a8bca8a3f23.png)
![RemoveContainer_WS2019_d32s_v3](https://user-images.githubusercontent.com/7319830/137919675-0c53d6ac-0c2c-4333-a540-5688e2c547d7.png)
![RemoveContainer_WS2022_d32s_v3](https://user-images.githubusercontent.com/7319830/137923577-b578df5c-341c-40e9-9aba-f6da17ca47dc.png)





