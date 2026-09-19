# Bài tập tính tay SNN — 3 Layer Classification

## 1. Mục tiêu

Tự tính **forward pass** của một mô hình SNN đơn giản gồm:

- 3 input neurons
- 4 timesteps
- 3 layers
- Classification với 2 output classes
- Có membrane potential
- Có threshold
- Có reset sau khi spike
- Decode bằng **spike count**

> **Lưu ý:** Bài này chỉ yêu cầu tính **forward**, chưa tính loss, backpropagation hay cập nhật weight.

---

# 2. Kiến trúc mô hình

```text
Input → Layer 1 → Layer 2 → Layer 3
 3N        2N         2N         2N
```

Trong đó:

- Input: 3 neurons
- Layer 1: 2 neurons
- Layer 2: 2 neurons
- Layer 3: 2 neurons
- Layer 3 là output layer
- Tổng số timestep:

$$
T=4
$$

---

# 3. Công thức SNN

Với mỗi neuron:

### Synaptic input

$$
I_j(t)=\sum_i W_{ji}S_i(t)
$$

### Membrane potential

$$
V_j(t)=V_j(t-1)+I_j(t)
$$

Nếu:

$$
V_j(t)\geq V_{th}
$$

thì neuron phát spike:

$$
S_j(t)=1
$$

và sau đó reset:

$$
V_j(t)=0
$$

Nếu:

$$
V_j(t)<V_{th}
$$

thì:

$$
S_j(t)=0
$$

và giữ nguyên membrane potential cho timestep tiếp theo.

Threshold của toàn bộ mô hình:

$$
V_{th}=1
$$

---

# 4. Input

Có 3 input neurons, mỗi neuron có 4 timesteps:

$$
S_{in}=
\begin{bmatrix}
0&1&0&1\\
1&1&0&0\\
0&0&1&1
\end{bmatrix}
$$

Hay:

```text
Neuron 1: [0, 1, 0, 1]
Neuron 2: [1, 1, 0, 0]
Neuron 3: [0, 0, 1, 1]
```

Tại từng timestep:

```text
t = 1 → [0, 1, 0]
t = 2 → [1, 1, 0]
t = 3 → [0, 0, 1]
t = 4 → [1, 0, 1]
```

---

# 5. Layer 1

Layer 1 có 2 neurons.

Weight:

$$
W_1=
\begin{bmatrix}
0.5&0.5&0.5\\
0.3&0.7&0.3
\end{bmatrix}
$$

Ban đầu:

$$
V_1(0)=0
$$

$$
V_2(0)=0
$$

## Nhiệm vụ

Tính lần lượt:

$$
t=1,2,3,4
$$

Với mỗi timestep:

1. Lấy input spike.
2. Tính \(I_1,I_2\).
3. Cập nhật \(V_1,V_2\).
4. Kiểm tra threshold.
5. Xác định spike.
6. Reset membrane potential nếu neuron spike.

Kết quả cần tìm:

$$
S^{(1)}=
\begin{bmatrix}
?&?&?&?\\
?&?&?&?
\end{bmatrix}
$$

---

## Bảng tính Layer 1

| t   | Input     | \(I_1\) | \(V_1\) | \(S_1\) | \(I_2\) | \(V_2\) | \(S_2\) |
| --- | --------- | ------: | ------: | ------: | ------: | ------: | ------: |
| 1   | `[0,1,0]` |       ? |       ? |       ? |       ? |       ? |       ? |
| 2   | `[1,1,0]` |       ? |       ? |       ? |       ? |       ? |       ? |
| 3   | `[0,0,1]` |       ? |       ? |       ? |       ? |       ? |       ? |
| 4   | `[1,0,1]` |       ? |       ? |       ? |       ? |       ? |       ? |

---

# 6. Layer 2

Output của Layer 1 trở thành input của Layer 2.

Layer 2 có 2 neurons.

Weight:

$$
W_2=
\begin{bmatrix}
0.6&0.4\\
0.4&0.6
\end{bmatrix}
$$

Ban đầu:

$$
V_1(0)=0
$$

$$
V_2(0)=0
$$

Sử dụng cùng công thức:

$$
I_j(t)=\sum_i W_{ji}S_i(t)
$$

$$
V_j(t)=V_j(t-1)+I_j(t)
$$

Nếu:

$$
V_j(t)\geq1
$$

thì:

$$
S_j(t)=1
$$

và reset:

$$
V_j(t)=0
$$

## Nhiệm vụ

Lấy output của Layer 1 làm input và tính toàn bộ 4 timesteps.

Kết quả:

$$
S^{(2)}=
\begin{bmatrix}
?&?&?&?\\
?&?&?&?
\end{bmatrix}
$$

---

## Bảng tính Layer 2

| t   | Input   | \(I_1\) | \(V_1\) | \(S_1\) | \(I_2\) | \(V_2\) | \(S_2\) |
| --- | ------- | ------: | ------: | ------: | ------: | ------: | ------: |
| 1   | `[...]` |       ? |       ? |       ? |       ? |       ? |       ? |
| 2   | `[...]` |       ? |       ? |       ? |       ? |       ? |       ? |
| 3   | `[...]` |       ? |       ? |       ? |       ? |       ? |       ? |
| 4   | `[...]` |       ? |       ? |       ? |       ? |       ? |       ? |

---

# 7. Layer 3 — Output Layer

Layer 3 có 2 neurons.

Hai neurons đại diện cho:

```text
Neuron 1 → Class 0
Neuron 2 → Class 1
```

Weight:

$$
W_3=
\begin{bmatrix}
0.7&0.3\\
0.3&0.7
\end{bmatrix}
$$

Ban đầu:

$$
V_1(0)=0
$$

$$
V_2(0)=0
$$

Threshold:

$$
V_{th}=1
$$

---

## Nhiệm vụ

Lấy output của Layer 2 làm input cho Layer 3.

Tính:

$$
t=1,2,3,4
$$

Kết quả cần tìm:

$$
S^{(3)}=
\begin{bmatrix}
?&?&?&?\\
?&?&?&?
\end{bmatrix}
$$

---

## Bảng tính Layer 3

| t   | Input   | \(I_1\) | \(V_1\) | \(S_1\) | \(I_2\) | \(V_2\) | \(S_2\) |
| --- | ------- | ------: | ------: | ------: | ------: | ------: | ------: |
| 1   | `[...]` |       ? |       ? |       ? |       ? |       ? |       ? |
| 2   | `[...]` |       ? |       ? |       ? |       ? |       ? |       ? |
| 3   | `[...]` |       ? |       ? |       ? |       ? |       ? |       ? |
| 4   | `[...]` |       ? |       ? |       ? |       ? |       ? |       ? |

---

# 8. Decode — Classification

Sau khi tính xong Layer 3, ta có spike train của 2 output neurons.

Ví dụ dạng:

```text
Class 0: [?, ?, ?, ?]
Class 1: [?, ?, ?, ?]
```

Đếm số spike của từng neuron:

$$
Count_0=\sum_{t=1}^{4}S_0(t)
$$

$$
Count_1=\sum_{t=1}^{4}S_1(t)
$$

Sau đó:

$$
\hat y=\arg\max(Count_0,Count_1)
$$

Quy tắc:

```text
Nếu Count_0 > Count_1
→ Prediction = Class 0

Nếu Count_1 > Count_0
→ Prediction = Class 1
```

---

# 9. Flow tổng thể

```text
Input Spike
    │
    │ 3 neurons × 4 timesteps
    ▼
┌────────────┐
│  Layer 1   │
│  2 neurons │
└────────────┘
    │
    │ Spike output
    ▼
┌────────────┐
│  Layer 2   │
│  2 neurons │
└────────────┘
    │
    │ Spike output
    ▼
┌────────────┐
│  Layer 3   │
│  2 neurons │
│ Output     │
└────────────┘
    │
    ▼
Spike Matrix
    │
    ▼
Spike Count
    │
    ▼
argmax
    │
    ▼
Prediction
```

---

# 10. Mục tiêu cần hoàn thành

Sau khi làm xong, cần có:

### Layer 1

$$
S^{(1)}=?
$$

### Layer 2

$$
S^{(2)}=?
$$

### Layer 3

$$
S^{(3)}=?
$$

### Spike count

$$
[Count_0,Count_1]=?
$$

### Prediction

$$
\boxed{\hat y=?}
$$

> **Chưa cần làm:** Loss, Backpropagation, Surrogate Gradient, BPTT và cập nhật \(W,b\).
