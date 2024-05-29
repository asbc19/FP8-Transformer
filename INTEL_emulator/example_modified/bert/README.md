
# INTEL Information
1. Prerequisite:
Install squad task-specific requirements (one time):  
`pip install -r requirements.txt`

2. Download SQUAD dataset:  
`bash download_squad_dataset.sh`

3. Download Squad fine-tuned model for inference:  
`bash download_squad_fine_tuned_model.sh`

4. To run squad baseline inference task:  
`bash cmd_infer.sh` 

5. To run squad inference in BF8:  
`bash cmd_infer.sh --use_pcl --pcl_bf8 --unpad`

# Extra Information
Datasets SQUAD1 and 2 can be found here:
1. `\SQUAD1`:  
  https://sutdapac-my.sharepoint.com/:f:/g/personal/brito_andres_mymail_sutd_edu_sg/EgsCSdflsC9PhQGga9qqqSYBcsSjFPWwdhLd7iy0VH2_qw?e=4076eA
2. `\SQUAD2`:  
  https://sutdapac-my.sharepoint.com/:f:/g/personal/brito_andres_mymail_sutd_edu_sg/Etw1ih1o1YBNl9S0U6xdeAwBVc738aK6TQs4t7Vnu13jng?e=8Qdh76
