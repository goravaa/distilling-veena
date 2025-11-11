
## 🧪 Veena TTS — Generation Benchmark (GPU: T4)

### 🔉 Hindi

**Speaker:** `kavya`

```
Generation: 52.17 s  
Decode:      1.71 s  
Total:      53.88 s
```

---

### 🔉 English

**Speaker:** `agastya`

```
Generation: 39.88 s  
Decode:      0.04 s  
Total:      39.92 s
```

---

### 🔉 Code-Mixed (Hinglish)

**Speaker:** `maitri`

```
Generation: 35.25 s  
Decode:      0.04 s  
Total:      35.28 s
```

---

## ⚙️ Model Architecture Summary

```text
LlamaForCausalLM(
  (model): LlamaModel(
    (embed_tokens): Embedding(156951, 3072)
    (layers): ModuleList(
      (0–27): 28 × LlamaDecoderLayer(
        (self_attn): LlamaAttention(
          (q_proj): Linear4bit(3072 → 3072, bias=False)
          (k_proj): Linear4bit(3072 → 1024, bias=False)
          (v_proj): Linear4bit(3072 → 1024, bias=False)
          (o_proj): Linear4bit(3072 → 3072, bias=False)
        )
        (mlp): LlamaMLP(
          (gate_proj): Linear4bit(3072 → 8192, bias=False)
          (up_proj):   Linear4bit(3072 → 8192, bias=False)
          (down_proj): Linear4bit(8192 → 3072, bias=False)
          (act_fn): SiLU
        )
        (input_layernorm):  LlamaRMSNorm((3072,), eps=1e−5)
        (post_attention_layernorm): LlamaRMSNorm((3072,), eps=1e−5)
      )
    )
    (norm): LlamaRMSNorm((3072,), eps=1e−5)
    (rotary_emb): LlamaRotaryEmbedding()
  )
  (lm_head): Linear(3072 → 156951, bias=False)
)
```

---

### 🧾 Notes

* Quantized 4-bit inference on **T4 (16 GB)**
* Average latency per sentence: **35–50 s** (depends on length)
* SNAC decoding adds < 2 s overhead
* Architecture: 28-layer, 3072-hidden Llama backbone with SNAC audio head
