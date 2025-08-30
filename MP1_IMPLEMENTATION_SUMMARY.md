# CS598JBR MP1 Implementation Summary

## Overview
This repository contains the complete implementation for MP1 (Machine Programming Assignment 1) which evaluates code generation capabilities of Large Language Models using the HumanEval dataset.

## What We've Accomplished

### 1. ✅ Repository Setup
- Updated team NetIDs: [muthigi2, ritikh2, sgnayak2, ya11]
- Configured GitHub repository: https://github.com/muthigi2/CS598JBR-Team-9
- Updated README.md with team information

### 2. ✅ Dataset Generation
- Successfully generated unique dataset based on team NetIDs
- Seed: 131515897657672734932032441166005753609
- Generated files:
  - `MP1/selected_humaneval_131515897657672734932032441166005753609.jsonl` (20 problems)
  - `MP1/humaneval.jsonl` (complete dataset)

### 3. ✅ Model Implementation
- Completed `MP1/model_prompting.py` with all required TODO items:
  - Model downloading and tokenizer setup
  - Quantization configuration using BitsAndBytesConfig
  - Model loading with/without quantization
  - Model prompting with proper parameters (temperature=0.0, greedy decoding)
  - Post-processing implementation to fix indentation and remove extraneous code

### 4. ✅ Environment Setup
- Created Python virtual environment
- Installed all required dependencies:
  - datasets, jsonlines, torch, transformers, bitsandbytes
  - peft, accelerate, einops, evaluate, sentencepiece
  - human-eval evaluation package
  - pandas, colorama for analysis

### 5. ✅ Jupyter Notebook
- Created comprehensive notebook: `CS598JBR-Team-9.ipynb`
- Includes all sections from setup to evaluation
- Ready to run on local environment with GPU
- Implements complete workflow from dataset generation to results analysis

### 6. ✅ Configuration Files
- Updated `MP1/commands.py` with correct NetIDs and GitHub repository
- Modified temperature and torch_dtype settings according to requirements
- Set up proper file naming conventions

## Files Generated and Ready for Execution

### Required Deliverables Structure
```
MP1/
├── selected_humaneval_{seed}.jsonl          ✅ Ready
├── dataset_generation.log                   ⏳ Generated when notebook runs
├── base_prompt_{seed}.jsonl                 ⏳ Generated when models run
├── base_prompt_processed_{seed}.jsonl       ⏳ Generated when models run  
├── instruct_prompt_{seed}.jsonl             ⏳ Generated when models run
├── instruct_prompt_processed_{seed}.jsonl   ⏳ Generated when models run
├── base_prompt_{seed}.jsonl_results.jsonl   ⏳ Generated when evaluation runs
├── base_prompt_processed_{seed}.jsonl_results.jsonl  ⏳ Generated when evaluation runs
├── instruct_prompt_{seed}.jsonl_results.jsonl        ⏳ Generated when evaluation runs
├── instruct_prompt_processed_{seed}.jsonl_results.jsonl  ⏳ Generated when evaluation runs
├── base_prompt.log                          ⏳ Generated when models run
├── instruct_prompt.log                      ⏳ Generated when models run
├── base_evaluate.log                        ⏳ Generated when evaluation runs
├── instruct_evaluate.log                    ⏳ Generated when evaluation runs
├── base_evaluate_processed.log              ⏳ Generated when evaluation runs
└── instruct_evaluate_processed.log          ⏳ Generated when evaluation runs
```

## Next Steps

### To Complete MP1:

1. **Run the Jupyter Notebook** (`CS598JBR-Team-9.ipynb`):
   - Requires GPU access for model loading
   - Will generate all remaining required files
   - Includes automatic evaluation and analysis

2. **Google Colab Setup** (Alternative):
   - Upload the notebook to Google Colab
   - Set runtime to T4 GPU
   - Run all cells in sequence

3. **Commit Results**:
   - All generated files will be created in correct locations
   - Commit everything to GitHub repository
   - Invite instructors and TAs as collaborators

4. **Progress Report**:
   - Include pass@k analysis from generated results
   - Create comparison table from evaluation outputs
   - Analyze post-processing effectiveness

## Technical Details

### Model Configuration
- **Models**: DeepSeekCoder-6.7b-base and DeepSeekCoder-6.7b-instruct
- **Quantization**: 4-bit quantization using BitsAndBytesConfig
- **Generation Settings**: temperature=0.0, greedy decoding, max_new_tokens=512
- **Data Type**: torch.bfloat16 as specified

### Post-Processing Features
- Removes extraneous output after function completion
- Fixes indentation issues
- Handles multi-function responses by extracting only the target function
- Preserves code logic while cleaning formatting

### Evaluation Process
- Uses human-eval package's `evaluate_functional_correctness` function
- Generates detailed pass/fail results for each problem
- Calculates pass@k metrics automatically
- Creates comparison tables for analysis

## Validation
- `MP1/validate.py` script available for checking deliverable structure
- All file naming follows autograder requirements
- Repository structure matches expected format

---

**Team**: CS598JBR-Team-9  
**Members**: Saurav Nayak, Yegu Sanjana Annamalai, Anil Muthigi, Ritik Hariani  
**Seed**: 131515897657672734932032441166005753609
