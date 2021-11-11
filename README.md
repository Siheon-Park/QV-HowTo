# 파일 설명
sdsqv.ipynb: 메인 주피터 노트북. 이 노트북에 모든 Figure, QPU runtime 등이 기록되어 있음. 또한, random circuit을 만들고, ideal simuation과 ibmq_toronto의 count를 엑셀파일로 저장함.

measureing-quantum-volume.ipynb: 템플렛 파일

local_simulation_with_noise.tar.gz: local backend with noise model로 실험한 경우 QV결과

qv_fitter: dill 패키지로 저장한 qv_fitter 바이너리 파일. (sdsqv.ipynb 참조)

로드 방법:
~~~ python
import dill
with open('./qv_fitter', 'rb') as f:
    qv_fitter = dill.load(f)
~~~

temp.py: [Rx, Ry, Rx, CNOT]으로 구성된 Random circuit을 제작하기 위한 파일.

counts(ideal).xlsx: ideal simulation에서 random circuit의 count

counts(real).xlsx: ibmq_toronto에서 random circuit의 count

random_circuits: dill 패키지로 저장한 random circuit 바이너리 파일. (sdsqv.ipynb 참조 ) list 객체로 [4, 5, 6, 7, 8, 9] 개수의 큐빗에 해당하는 QuantumCircuit을 저장

로드 방법:
~~~ python
import dill
with open('./random_circuits', 'rb') as f:
    random_circuits = dill.load(f)
~~~

# Summary
QPU: ibmq_toronto

shots: 2^13

number of trials (for QV calculation): 100

number of trials (for random circuits): 100

Execution time purly in QPU for QV: 3101.4567573070526s

QV number of qubits:  [4, 5, 6, 7, 8, 9]

Used Qubits: [0, 1, 2, 3, 5, 8, 11, 14, 16] (9 qubits)

QV success rate    :  ['40.97%', '7.44%', '0.16%', '0.15%', '0.05%', '0.05%']

QPU: ibmq_toronto

Execution time purly in QPU for counts: 2735.9472148418427s

random circuits: saved at ./random_circuits (binary)