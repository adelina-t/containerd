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
