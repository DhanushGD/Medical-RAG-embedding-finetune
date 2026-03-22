---
language:
- en
tags:
- sentence-transformers
- sentence-similarity
- feature-extraction
- dense
- generated_from_trainer
- dataset_size:10000
- loss:MultipleNegativesRankingLoss
base_model: unsloth/all-MiniLM-L6-v2
widget:
- source_sentence: 'Epidural analgesia for surgical treatment of peritoneal carcinomatosis:
    a risky technique?'
  sentences:
  - The 1990 national Youth Risk Behavior Survey was used to collect self-reported
    information about a broad range of health risk behaviors from a representative
    sample of 11,631 high school students in the United States.
  - We retrospectively analyzed the data of 35 patients treated by HIPEC with oxaliplatin
    or cisplatin. An epidural catheter was inserted before induction of general anaesthesia.
    Postoperatively, a continuous epidural infusion of ropivacain, then a patient-controlled
    epidural analgesia were started.
  - Prior studies suggest a possible association between the use of neuraxial-general
    anesthesia and a decrease in prostate cancer recurrence after radical prostatectomy.
    We examine the correlation of a spinal anesthesia-only technique on prostate cancer
    recurrence.
- source_sentence: Does sonographic needle guidance affect the clinical outcome of
    intraarticular injections?
  sentences:
  - This randomized controlled study addressed whether sonographic needle guidance
    affected clinical outcomes of intraarticular (IA) joint injections.
  - Allegheny General Hospital, Pittsburgh, Pennsylvania.
  - The purpose of this study was to evaluate how intravascular ultrasound-determined
    thickness and reflectivity of the inner echogenic layer of coronary artery plaque
    is affected by changes in collagen, elastin, proteoglycan, calcium and lipid content
    in the intima and media.
- source_sentence: 'The FOOTSTEP self-management foot care programme: are rheumatoid
    arthritis patients physically able to participate?'
  sentences:
  - To measure and compare patient satisfaction with follow-up care in advanced practice
    physiotherapist (APP) and orthopaedic surgeon clinics for patients following total
    hip or knee replacement.
  - The FOOTSTEP self-management foot care programme is a clinical and cost-effective
    programme for basic foot care in the elderly. The aim of this study was to determine
    if patients with rheumatoid arthritis (RA) would be physically able to participate.
  - Three hundred fifty-three consecutive obstructive sleep apnea (OSA) patients who
    had a successful manual CPAP titration in our sleep disorders unit.
- source_sentence: 'Major depression and alcohol use disorder in adolescence: Does
    comorbidity lead to poorer outcomes of depression?'
  sentences:
  - The three disorder groups had rates of adult MD during the period 18-35 years
    that were significantly (p<.05) higher than that of the group with no disorder.
    Furthermore, those in the comorbid MD/AUD group had significantly (p<.05) higher
    rates of adult MD than those in the AUD-only group, and marginally (p<.10) higher
    rates of adult MD than those in the MD-only group. After adjustment for confounding,
    the difference in rates of adult MD between the MD-only group and the MD/AUD group
    were no longer statistically significant. The factors that explained the associations
    were gender, childhood behavior problems, and exposure to physical and sexual
    abuse.
  - Pneumothorax following flexible bronchoscopy (FB) with transbronchial biopsy (TBB)
    occurs in 1 to 6% of cases. Routine chest radiography (CXR) following TBB is therefore
    requested by most pulmonologists in an attempt to detect complications, particularly
    pneumothorax. The objective of this study was to determine if routine CXR after
    bronchoscopy and TBB is necessary.
  - Previous research has shown that as people age, distress decreases despite an
    increase in prevalence of medical comorbidity. This could be due to increased
    use of psychotropic medications with comorbidity. We tested this hypothesis in
    older adults.
- source_sentence: 'Israeli hospital preparedness for terrorism-related multiple casualty
    incidents: can the surge capacity and injury severity distribution be better predicted?'
  sentences:
  - Forty-six consecutive patients, of whom 21 were male and 25 were female (mean
    age, 55.6 years; range, 15-80 years). Previous antireflux procedures were laparoscopic
    (21 patients), laparotomy (21 patients), thoracotomy (3 patients), and thoracoscopy
    (1 patient).
  - Which intervention(s) best augment early mobilisation and external support after
    an acute ankle sprain? What is the most appropriate method of preventing re-injury?
  - The incidence of large-scale urban attacks on civilian populations has significantly
    increased across the globe over the past decade. These incidents often result
    in Hospital Multiple Casualty Incidents (HMCI), which are very challenging to
    hospital teams. 15 years ago the Emergency and Disaster Medicine Division in the
    Israeli Ministry of Health defined a key of 20 percent of each hospital's bed
    capacity as its readiness for multiple casualties. Half of those casualties are
    expected to require immediate medical treatment. This study was performed to evaluate
    the efficacy of the current readiness guidelines based on the epidemiology of
    encountered HMCIs.
datasets:
- sentence-transformers/pubmedqa
pipeline_tag: sentence-similarity
library_name: sentence-transformers
metrics:
- cosine_accuracy@1
- cosine_accuracy@3
- cosine_accuracy@5
- cosine_accuracy@10
- cosine_precision@1
- cosine_precision@3
- cosine_precision@5
- cosine_precision@10
- cosine_recall@1
- cosine_recall@3
- cosine_recall@5
- cosine_recall@10
- cosine_ndcg@10
- cosine_mrr@10
- cosine_map@100
model-index:
- name: SentenceTransformer based on unsloth/all-MiniLM-L6-v2
  results:
  - task:
      type: information-retrieval
      name: Information Retrieval
    dataset:
      name: PubMedQA Medical Eval
      type: PubMedQA_Medical_Eval
    metrics:
    - type: cosine_accuracy@1
      value: 0.374
      name: Cosine Accuracy@1
    - type: cosine_accuracy@3
      value: 0.744
      name: Cosine Accuracy@3
    - type: cosine_accuracy@5
      value: 0.846
      name: Cosine Accuracy@5
    - type: cosine_accuracy@10
      value: 0.889
      name: Cosine Accuracy@10
    - type: cosine_precision@1
      value: 0.374
      name: Cosine Precision@1
    - type: cosine_precision@3
      value: 0.248
      name: Cosine Precision@3
    - type: cosine_precision@5
      value: 0.1692
      name: Cosine Precision@5
    - type: cosine_precision@10
      value: 0.0889
      name: Cosine Precision@10
    - type: cosine_recall@1
      value: 0.374
      name: Cosine Recall@1
    - type: cosine_recall@3
      value: 0.744
      name: Cosine Recall@3
    - type: cosine_recall@5
      value: 0.846
      name: Cosine Recall@5
    - type: cosine_recall@10
      value: 0.889
      name: Cosine Recall@10
    - type: cosine_ndcg@10
      value: 0.6462179536732854
      name: Cosine Ndcg@10
    - type: cosine_mrr@10
      value: 0.5660924603174604
      name: Cosine Mrr@10
    - type: cosine_map@100
      value: 0.5693820527061744
      name: Cosine Map@100
---

# SentenceTransformer based on unsloth/all-MiniLM-L6-v2

This is a [sentence-transformers](https://www.SBERT.net) model finetuned from [unsloth/all-MiniLM-L6-v2](https://huggingface.co/unsloth/all-MiniLM-L6-v2) on the [pubmedqa](https://huggingface.co/datasets/sentence-transformers/pubmedqa) dataset. It maps sentences & paragraphs to a 384-dimensional dense vector space and can be used for semantic textual similarity, semantic search, paraphrase mining, text classification, clustering, and more.

## Model Details

### Model Description
- **Model Type:** Sentence Transformer
- **Base model:** [unsloth/all-MiniLM-L6-v2](https://huggingface.co/unsloth/all-MiniLM-L6-v2) <!-- at revision 0f79ca30c044e92859f5852d3a29fb6e976741cd -->
- **Maximum Sequence Length:** 256 tokens
- **Output Dimensionality:** 384 dimensions
- **Similarity Function:** Cosine Similarity
- **Training Dataset:**
    - [pubmedqa](https://huggingface.co/datasets/sentence-transformers/pubmedqa)
- **Language:** en
<!-- - **License:** Unknown -->

### Model Sources

- **Documentation:** [Sentence Transformers Documentation](https://sbert.net)
- **Repository:** [Sentence Transformers on GitHub](https://github.com/huggingface/sentence-transformers)
- **Hugging Face:** [Sentence Transformers on Hugging Face](https://huggingface.co/models?library=sentence-transformers)

### Full Model Architecture

```
SentenceTransformer(
  (0): Transformer({'max_seq_length': 256, 'do_lower_case': False, 'architecture': 'PeftModelForFeatureExtraction'})
  (1): Pooling({'word_embedding_dimension': 384, 'pooling_mode_cls_token': False, 'pooling_mode_mean_tokens': True, 'pooling_mode_max_tokens': False, 'pooling_mode_mean_sqrt_len_tokens': False, 'pooling_mode_weightedmean_tokens': False, 'pooling_mode_lasttoken': False, 'include_prompt': True})
  (2): Normalize()
)
```

## Usage

### Direct Usage (Sentence Transformers)

First install the Sentence Transformers library:

```bash
pip install -U sentence-transformers
```

Then you can load this model and run inference.
```python
from sentence_transformers import SentenceTransformer

# Download from the 🤗 Hub
model = SentenceTransformer("sentence_transformers_model_id")
# Run inference
sentences = [
    'Israeli hospital preparedness for terrorism-related multiple casualty incidents: can the surge capacity and injury severity distribution be better predicted?',
    "The incidence of large-scale urban attacks on civilian populations has significantly increased across the globe over the past decade. These incidents often result in Hospital Multiple Casualty Incidents (HMCI), which are very challenging to hospital teams. 15 years ago the Emergency and Disaster Medicine Division in the Israeli Ministry of Health defined a key of 20 percent of each hospital's bed capacity as its readiness for multiple casualties. Half of those casualties are expected to require immediate medical treatment. This study was performed to evaluate the efficacy of the current readiness guidelines based on the epidemiology of encountered HMCIs.",
    'Which intervention(s) best augment early mobilisation and external support after an acute ankle sprain? What is the most appropriate method of preventing re-injury?',
]
embeddings = model.encode(sentences)
print(embeddings.shape)
# [3, 384]

# Get the similarity scores for the embeddings
similarities = model.similarity(embeddings, embeddings)
print(similarities)
# tensor([[1.0000, 0.7520, 0.2560],
#         [0.7520, 1.0000, 0.2255],
#         [0.2560, 0.2255, 1.0000]])
```

<!--
### Direct Usage (Transformers)

<details><summary>Click to see the direct usage in Transformers</summary>

</details>
-->

<!--
### Downstream Usage (Sentence Transformers)

You can finetune this model on your own dataset.

<details><summary>Click to expand</summary>

</details>
-->

<!--
### Out-of-Scope Use

*List how the model may foreseeably be misused and address what users ought not to do with the model.*
-->

## Evaluation

### Metrics

#### Information Retrieval

* Dataset: `PubMedQA_Medical_Eval`
* Evaluated with [<code>InformationRetrievalEvaluator</code>](https://sbert.net/docs/package_reference/sentence_transformer/evaluation.html#sentence_transformers.evaluation.InformationRetrievalEvaluator)

| Metric              | Value      |
|:--------------------|:-----------|
| cosine_accuracy@1   | 0.374      |
| cosine_accuracy@3   | 0.744      |
| cosine_accuracy@5   | 0.846      |
| cosine_accuracy@10  | 0.889      |
| cosine_precision@1  | 0.374      |
| cosine_precision@3  | 0.248      |
| cosine_precision@5  | 0.1692     |
| cosine_precision@10 | 0.0889     |
| cosine_recall@1     | 0.374      |
| cosine_recall@3     | 0.744      |
| cosine_recall@5     | 0.846      |
| cosine_recall@10    | 0.889      |
| **cosine_ndcg@10**  | **0.6462** |
| cosine_mrr@10       | 0.5661     |
| cosine_map@100      | 0.5694     |

<!--
## Bias, Risks and Limitations

*What are the known or foreseeable issues stemming from this model? You could also flag here known failure cases or weaknesses of the model.*
-->

<!--
### Recommendations

*What are recommendations with respect to the foreseeable issues? For example, filtering explicit content.*
-->

## Training Details

### Training Dataset

#### pubmedqa

* Dataset: [pubmedqa](https://huggingface.co/datasets/sentence-transformers/pubmedqa) at [a1ef0b5](https://huggingface.co/datasets/sentence-transformers/pubmedqa/tree/a1ef0b513b16ed490e807ac11da40e436d3a54c3)
* Size: 10,000 training samples
* Columns: <code>anchor</code>, <code>positive</code>, and <code>negative</code>
* Approximate statistics based on the first 1000 samples:
  |         | anchor                                                                            | positive                                                                           | negative                                                                           |
  |:--------|:----------------------------------------------------------------------------------|:-----------------------------------------------------------------------------------|:-----------------------------------------------------------------------------------|
  | type    | string                                                                            | string                                                                             | string                                                                             |
  | details | <ul><li>min: 8 tokens</li><li>mean: 21.51 tokens</li><li>max: 52 tokens</li></ul> | <ul><li>min: 4 tokens</li><li>mean: 94.45 tokens</li><li>max: 256 tokens</li></ul> | <ul><li>min: 5 tokens</li><li>mean: 73.29 tokens</li><li>max: 256 tokens</li></ul> |
* Samples:
  | anchor                                                                                                              | positive                                                                                                                                                                                                                                                                                                                                                                                                                                                                           | negative                                                                                                                                                                                                                                                                                                                                                                                                                                                            |
  |:--------------------------------------------------------------------------------------------------------------------|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|:--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
  | <code>Does solid culture for tuberculosis influence clinical decision making in India?</code>                       | <code>To investigate the impact of solid culture on Löwenstein-Jensen medium on clinical decision making.</code>                                                                                                                                                                                                                                                                                                                                                                   | <code>Ukraine's volatile syndemics of tuberculosis (TB) and HIV among people who inject drugs (PWIDs) introduces numerous treatment challenges for each condition, including high mortality and development of multi-drug resistant TB (MDR-TB).</code>                                                                                                                                                                                                             |
  | <code>Does successful completion of the Perinatal Education Programme result in improved obstetric practice?</code> | <code>The three midwife obstetric units (MOUs) in a health district of Mpumalanga were included in the study. Two MOUs enrolled in the PEP and the third did not. A 'before-and-after' study design was used to assess any changes in practice, and to monitor whether any changes occurred in the district during the time of the study; data were also collected at the third MOU. Data were collected by scoring of the obstetric files after the patient had delivered.</code> | <code>Infertility clinic in a university hospital.</code>                                                                                                                                                                                                                                                                                                                                                                                                           |
  | <code>Is anorectal endosonography valuable in dyschesia?</code>                                                     | <code>Dyschesia can be provoked by inappropriate defecation movements. The aim of this prospective study was to demonstrate dysfunction of the anal sphincter and/or the musculus (m.) puborectalis in patients with dyschesia using anorectal endosonography.</code>                                                                                                                                                                                                              | <code>Poor bone density may affect surgical planning, treatment outcome, and postoperative protocols. Many patients with foot and ankle problems have not undergone a dual x-ray absorptiometry (DXA) scan, which is currently the gold standard for determining bone density. The purpose of this study was to determine if the cortical bone thickness (CBT) of the distal part of the tibia measured on radiographs correlated with bone mineral density.</code> |
* Loss: [<code>MultipleNegativesRankingLoss</code>](https://sbert.net/docs/package_reference/sentence_transformer/losses.html#multiplenegativesrankingloss) with these parameters:
  ```json
  {
      "scale": 20.0,
      "similarity_fct": "cos_sim",
      "gather_across_devices": false
  }
  ```

### Evaluation Dataset

#### pubmedqa

* Dataset: [pubmedqa](https://huggingface.co/datasets/sentence-transformers/pubmedqa) at [a1ef0b5](https://huggingface.co/datasets/sentence-transformers/pubmedqa/tree/a1ef0b513b16ed490e807ac11da40e436d3a54c3)
* Size: 1,000 evaluation samples
* Columns: <code>anchor</code>, <code>positive</code>, and <code>negative</code>
* Approximate statistics based on the first 1000 samples:
  |         | anchor                                                                            | positive                                                                           | negative                                                                           |
  |:--------|:----------------------------------------------------------------------------------|:-----------------------------------------------------------------------------------|:-----------------------------------------------------------------------------------|
  | type    | string                                                                            | string                                                                             | string                                                                             |
  | details | <ul><li>min: 8 tokens</li><li>mean: 22.05 tokens</li><li>max: 52 tokens</li></ul> | <ul><li>min: 4 tokens</li><li>mean: 93.12 tokens</li><li>max: 256 tokens</li></ul> | <ul><li>min: 5 tokens</li><li>mean: 72.56 tokens</li><li>max: 256 tokens</li></ul> |
* Samples:
  | anchor                                                                                                                   | positive                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             | negative                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                |
  |:-------------------------------------------------------------------------------------------------------------------------|:---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|:--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
  | <code>Does music influence stress in mechanically ventilated patients?</code>                                            | <code>Urinary free cortisol (UFC), an integrative biomarker of stress.</code>                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        | <code>The settings of mechanical ventilation, like tidal volume (VT), occasionally need to be adjusted in the process of anesthesia for some special reasons. The aim of this study was therefore to assess the relationship between pulse pressure variations (PPVs) in different settings of VT in anesthetized healthy patients under mechanical ventilation.</code>                                                                                                                                                                                                                                                                                                                                                                                 |
  | <code>Sternal plating for primary and secondary sternal closure; can it improve sternal stability?</code>                | <code>Midline sternotomy was performed in 18 human cadavers. Four sternal closure techniques were tested: (1) approximation with six interrupted steel wires; (2) approximation with six interrupted cables; (3) closure 1 (wires) or 2 (cables) reinforced with a transverse sternal plate at the sixth rib; (4) Closure using 4 sternal plates alone. Intrathoracic pressure was increased in all techniques while sternal separation was measured by three pairs of sonomicrometry crystals fixed at the upper, middle and lower parts of the sternum until 2.0 mm separation was detected. Differences in displacement pressures were analyzed using repeated measures ANOVA and Regression Coefficients.</code> | <code>There is an ongoing debate about the best closure technique after distal pancreatectomy (DP). The aim of the closure is to prevent the formation of a clinically relevant post-operative pancreatic fistula (POPF). Stapler technique seems to be equal compared with hand-sewn closure of the remnant. For both techniques, a fistula rate of approximately 30% has been reported.</code>                                                                                                                                                                                                                                                                                                                                                        |
  | <code>Does the aggressive use of polyvalent antivenin for rattlesnake bites result in serious acute side effects?</code> | <code>Primary outcome variables were the occurrence of immediate hypersensitivity reaction to antivenin, the type of reaction, permanent disability at hospital discharge, and mortality.</code>                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     | <code>Twelve patients were recruited and, based on their skin test results, all were treated with yellow jacket (YJ) venom, either alone or combined with other venoms. All 8 patients who were sting challenged by VO demonstrated positive skin test responses to VO venom. Six of the stung patients tolerated the sting challenge uneventfully. Two patients developed minimal transient symptoms that resolved spontaneously. SDS-PAGE with patient sera suggested cross-reactivity between VO and YJ venoms at molecular weights of 39-42 kDa. Using phospholipases, antigen 5 and hyaluronidase derived from several Vespa, Dolichovespula and Vespula species, hyaluronidase is possibly accountable for inducing the allergic reaction.</code> |
* Loss: [<code>MultipleNegativesRankingLoss</code>](https://sbert.net/docs/package_reference/sentence_transformer/losses.html#multiplenegativesrankingloss) with these parameters:
  ```json
  {
      "scale": 20.0,
      "similarity_fct": "cos_sim",
      "gather_across_devices": false
  }
  ```

### Training Hyperparameters
#### Non-Default Hyperparameters

- `eval_strategy`: steps
- `per_device_train_batch_size`: 32
- `per_device_eval_batch_size`: 32
- `learning_rate`: 2e-05
- `weight_decay`: 0.01
- `num_train_epochs`: 1
- `max_steps`: 100
- `warmup_ratio`: 0.1
- `fp16`: True
- `batch_sampler`: no_duplicates

#### All Hyperparameters
<details><summary>Click to expand</summary>

- `overwrite_output_dir`: False
- `do_predict`: False
- `eval_strategy`: steps
- `prediction_loss_only`: True
- `per_device_train_batch_size`: 32
- `per_device_eval_batch_size`: 32
- `per_gpu_train_batch_size`: None
- `per_gpu_eval_batch_size`: None
- `gradient_accumulation_steps`: 1
- `eval_accumulation_steps`: None
- `torch_empty_cache_steps`: None
- `learning_rate`: 2e-05
- `weight_decay`: 0.01
- `adam_beta1`: 0.9
- `adam_beta2`: 0.999
- `adam_epsilon`: 1e-08
- `max_grad_norm`: 1.0
- `num_train_epochs`: 1
- `max_steps`: 100
- `lr_scheduler_type`: linear
- `lr_scheduler_kwargs`: {}
- `warmup_ratio`: 0.1
- `warmup_steps`: 0
- `log_level`: passive
- `log_level_replica`: warning
- `log_on_each_node`: True
- `logging_nan_inf_filter`: True
- `save_safetensors`: True
- `save_on_each_node`: False
- `save_only_model`: False
- `restore_callback_states_from_checkpoint`: False
- `no_cuda`: False
- `use_cpu`: False
- `use_mps_device`: False
- `seed`: 42
- `data_seed`: None
- `jit_mode_eval`: False
- `use_ipex`: False
- `bf16`: False
- `fp16`: True
- `fp16_opt_level`: O1
- `half_precision_backend`: auto
- `bf16_full_eval`: False
- `fp16_full_eval`: False
- `tf32`: None
- `local_rank`: 0
- `ddp_backend`: None
- `tpu_num_cores`: None
- `tpu_metrics_debug`: False
- `debug`: []
- `dataloader_drop_last`: False
- `dataloader_num_workers`: 0
- `dataloader_prefetch_factor`: None
- `past_index`: -1
- `disable_tqdm`: False
- `remove_unused_columns`: True
- `label_names`: None
- `load_best_model_at_end`: False
- `ignore_data_skip`: False
- `fsdp`: []
- `fsdp_min_num_params`: 0
- `fsdp_config`: {'min_num_params': 0, 'xla': False, 'xla_fsdp_v2': False, 'xla_fsdp_grad_ckpt': False}
- `fsdp_transformer_layer_cls_to_wrap`: None
- `accelerator_config`: {'split_batches': False, 'dispatch_batches': None, 'even_batches': True, 'use_seedable_sampler': True, 'non_blocking': False, 'gradient_accumulation_kwargs': None}
- `parallelism_config`: None
- `deepspeed`: None
- `label_smoothing_factor`: 0.0
- `optim`: adamw_torch_fused
- `optim_args`: None
- `adafactor`: False
- `group_by_length`: False
- `length_column_name`: length
- `ddp_find_unused_parameters`: None
- `ddp_bucket_cap_mb`: None
- `ddp_broadcast_buffers`: False
- `dataloader_pin_memory`: True
- `dataloader_persistent_workers`: False
- `skip_memory_metrics`: True
- `use_legacy_prediction_loop`: False
- `push_to_hub`: False
- `resume_from_checkpoint`: None
- `hub_model_id`: None
- `hub_strategy`: every_save
- `hub_private_repo`: None
- `hub_always_push`: False
- `hub_revision`: None
- `gradient_checkpointing`: False
- `gradient_checkpointing_kwargs`: None
- `include_inputs_for_metrics`: False
- `include_for_metrics`: []
- `eval_do_concat_batches`: True
- `fp16_backend`: auto
- `push_to_hub_model_id`: None
- `push_to_hub_organization`: None
- `mp_parameters`: 
- `auto_find_batch_size`: False
- `full_determinism`: False
- `torchdynamo`: None
- `ray_scope`: last
- `ddp_timeout`: 1800
- `torch_compile`: False
- `torch_compile_backend`: None
- `torch_compile_mode`: None
- `include_tokens_per_second`: False
- `include_num_input_tokens_seen`: False
- `neftune_noise_alpha`: None
- `optim_target_modules`: None
- `batch_eval_metrics`: False
- `eval_on_start`: False
- `use_liger_kernel`: False
- `liger_kernel_config`: None
- `eval_use_gather_object`: False
- `average_tokens_across_devices`: False
- `prompts`: None
- `batch_sampler`: no_duplicates
- `multi_dataset_batch_sampler`: proportional
- `router_mapping`: {}
- `learning_rate_mapping`: {}

</details>

### Training Logs
| Epoch  | Step | Training Loss | Validation Loss | PubMedQA_Medical_Eval_cosine_ndcg@10 |
|:------:|:----:|:-------------:|:---------------:|:------------------------------------:|
| 0.0160 | 5    | 0.9058        | -               | -                                    |
| 0.0319 | 10   | 1.0209        | -               | -                                    |
| 0.0479 | 15   | 0.8418        | -               | -                                    |
| 0.0639 | 20   | 1.1285        | 0.8193          | 0.6462                               |
| 0.0799 | 25   | 1.2714        | -               | -                                    |
| 0.0958 | 30   | 0.952         | -               | -                                    |
| 0.1118 | 35   | 0.8273        | -               | -                                    |
| 0.1278 | 40   | 0.6863        | 0.8193          | 0.6462                               |
| 0.1438 | 45   | 0.9249        | -               | -                                    |
| 0.1597 | 50   | 0.8148        | -               | -                                    |
| 0.1757 | 55   | 0.6137        | -               | -                                    |
| 0.1917 | 60   | 1.0901        | 0.8193          | 0.6462                               |
| 0.2077 | 65   | 0.8657        | -               | -                                    |
| 0.2236 | 70   | 0.7867        | -               | -                                    |
| 0.2396 | 75   | 1.078         | -               | -                                    |
| 0.2556 | 80   | 0.7171        | 0.8193          | 0.6462                               |
| 0.2716 | 85   | 1.0351        | -               | -                                    |
| 0.2875 | 90   | 0.9755        | -               | -                                    |
| 0.3035 | 95   | 0.8548        | -               | -                                    |
| 0.3195 | 100  | 1.0137        | 0.8193          | 0.6462                               |


### Framework Versions
- Python: 3.12.12
- Sentence Transformers: 5.2.3
- Transformers: 4.56.2
- PyTorch: 2.10.0+cu128
- Accelerate: 1.12.0
- Datasets: 4.3.0
- Tokenizers: 0.22.2

## Citation

### BibTeX

#### Sentence Transformers
```bibtex
@inproceedings{reimers-2019-sentence-bert,
    title = "Sentence-BERT: Sentence Embeddings using Siamese BERT-Networks",
    author = "Reimers, Nils and Gurevych, Iryna",
    booktitle = "Proceedings of the 2019 Conference on Empirical Methods in Natural Language Processing",
    month = "11",
    year = "2019",
    publisher = "Association for Computational Linguistics",
    url = "https://arxiv.org/abs/1908.10084",
}
```

#### MultipleNegativesRankingLoss
```bibtex
@misc{henderson2017efficient,
    title={Efficient Natural Language Response Suggestion for Smart Reply},
    author={Matthew Henderson and Rami Al-Rfou and Brian Strope and Yun-hsuan Sung and Laszlo Lukacs and Ruiqi Guo and Sanjiv Kumar and Balint Miklos and Ray Kurzweil},
    year={2017},
    eprint={1705.00652},
    archivePrefix={arXiv},
    primaryClass={cs.CL}
}
```

<!--
## Glossary

*Clearly define terms in order to be accessible across audiences.*
-->

<!--
## Model Card Authors

*Lists the people who create the model card, providing recognition and accountability for the detailed work that goes into its construction.*
-->

<!--
## Model Card Contact

*Provides a way for people who have updates to the Model Card, suggestions, or questions, to contact the Model Card authors.*
-->