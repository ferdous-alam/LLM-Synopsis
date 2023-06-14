## Details
LLM-Synopsis is a summary of recent large language models. I will try to update the table once a new model is realased. 

### OPT (META AI)

| # of params  |  125M, 350M, 6.7B, 13B, 30B, 66B, 175B  |
|-----------|-----------|
| # of tokens | 180B |
| dataset | The Pile (Common Crawl, Wikipedia, Gutenberg, Hackernews) |
| tokenizer | BPE |
|model architecture|transformer (decoder only)|
| training |<table><tr><td>model size</td><td>$n_\text{layer}$</td><td>$n_\text{head}$</td><td>$d_\text{model}$</td><td>lr</td><td>B</td></tr><tr><td>125M</td><td>12</td><td>12</td><td>768</td><td>6e-4</td><td>0.5M</td></tr><tr><td>350M</td><td>24</td><td>16</td><td>1024</td><td>3e-4</td><td>0.5M</td></tr><tr><tr><td>6.7B</td><td>32</td><td>32</td><td>4096</td><td>1.2e-4</td><td>2.0M</td></tr><tr><tr><td>13B</td><td>40</td><td>40</td><td>5120</td><td>1.0e-4</td><td>4.0M</td></tr><tr><td>30B</td><td>48</td><td>56</td><td>7168</td><td>1.0e-4</td><td>4M</td></tr><tr><td>66B</td><td>64</td><td>72</td><td>9216</td><td>0.8e-4</td><td>2.0M</td></tr><tr><tr><td>175B</td><td>96</td><td>96</td><td>12288</td><td>1.2e-4</td><td>2.0M</td></tr></table>|
|warm up| lr $\Rightarrow$ linear, B $\Rightarrow$ **True**|
|numerical| forward and backward pass (**BF16**), parameters (**FP32**)|
|hardware| 992 A100 80GB|
|evaluation| few-shot, zero-shot, dialogue|
|||


### LLAMA (META AI)

| # of params  |  7B, 13B, 33B, 65B  |
|-----------|-----------|
| # of tokens | 1.4T |
| dataset | CommonCrawl, Wikipedia, C4, Github, Books, ArXiv, StackExchange (dedup: **True**) |
| tokenizer | BPE |
|model architecture|transformer (decoder only)|
| optimizer |<table><tr><td>name</td><td>params</td></tr><tr><td>AdamW</td><td>$\beta_1=0.9, \beta_2=0.95$, weight decay = 0.1</td></tr></table>|
| training |<table><tr><td>model size</td><td>$n_\text{layer}$</td><td>$n_\text{head}$</td><td>$d_\text{model}$</td><td>lr</td><td>B</td></tr><tr><td>6.7B</td><td>32</td><td>32</td><td>4096</td><td>3e-4</td><td>4.0M</td></tr><tr><td>13B</td><td>40</td><td>40</td><td>5120</td><td>3e-4</td><td>4.0M</td></tr><tr><tr><td>32.5B</td><td>52</td><td>60</td><td>6656</td><td>1.5e-4</td><td>4.0M</td></tr><tr><tr><td>65.2B</td><td>64</td><td>80</td><td>8192</td><td>1.5e-4</td><td>4.0M</td></tr></table>|
|warm up| lr $\Rightarrow$ linear, B $\Rightarrow$ **True**|
|numerical| forward and backward pass (**BF16**), parameters (**FP32**)|
|hardware| 2048 A100 80GB|
|evaluation| few-shot, zero-shot|
|||


