What this new notebook does:
 Uses your Ground Truth CSV as seed data - samples real NVINFO Q&A pairs
 Generates NEW questions similar to the seed examples
 Creates answers using the original NVINFO content as context
 Maintains all 53 categories from your spreadsheet
 Quality scores each generated Q&A pair


Result:
nvinfo_generated_accurate.csv 
HIGH-QUALITY ONLY
Keeps only: HighlyRelevant AND Accurate
Removed: low-quality rows
Quality rate: ~50%


# Data-Designer
https://github.com/NVIDIA-NeMo/DataDesigner

1. Install
pip install data-designer


2.Set your API key
Start with one of our default model providers:

NVIDIA Build API
OpenAI
OpenRouter
endpoints of nemotron models

export NVIDIA_API_KEY="your-api-key-here"

export OPENAI_API_KEY="your-openai-api-key-here"

export OPENROUTER_API_KEY="your-openrouter-api-key-here"

export Internal_API_KEY="your-nemotron-key-here"

$ data-designer config providers

  ───────────────────────────────────────── Configure Model Providers ─────────────────────────────────────────

  💡  Configuration directory: /home/maggiez/.data-designer

  💡  Found 4 configured provider(s)

  ╭─ Current Configuration ───────────────────────────────────────────────────────────────────────────────────╮  
  │ providers:                                                                                                │  
  │ - name: nvidia                                                                                            │  
  │   endpoint: https://integrate.api.nvidia.com/v1                                                           │  
  │   provider_type: openai                                                                                   │  
  │   api_key: NVIDIA_API_KEY                                                                                 │  
  │ - name: openai                                                                                            │  
  │   endpoint: https://api.openai.com/v1                                                                     │  
  │   provider_type: openai                                                                                   │  
  │   api_key: OPENAI_API_KEY                                                                                 │  
  │ - name: openrouter                                                                                        │  
  │   endpoint: https://openrouter.ai/api/v1                                                                  │  
  │   provider_type: openai                                                                                   │  
  │   api_key: OPENROUTER_API_KEY                                                                             │  
  │ - name: nvcf                                                                                              │  
  │   endpoint: https://inference-api.nvidia.com                                                              │  
  │   provider_type: openai                                                                                   │  
  │   api_key: '***_KEY'                                                                                      │  
  │                                                                                                           │  
  ╰───────────────────────────────────────────────────────────────────────────────────────────────────────────╯  

$ jupyter notebook --no-browser


