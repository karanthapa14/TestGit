
# Python Script development to parse and extract test case info from DOCX file
## Objective
1. Search for that name in the attached word document where the “process” and when found, check if that has an associated table with it.
2. Pick that table and append it in a new spreadsheet giving it the same name as the two documents.
3. Continue with the same process till all the images are covered from the HTML document (HTML document is attached) and discovered in the Word Document (Word document is attached) and moved into the spreadsheet (Sample spreadsheet is attached). 
4. The spreadsheet should have the first column as the name of the block under t-code.
5. Once this set of document is successful and tested for completion, it will be tested for 5 more sets. These sets will be provided at a later stage.

## Prerequisites
### Installing Jupyter using Anaconda
Anaconda conveniently installs **Python** (currently Python 3.7) and **Jupyter Notebook**.
Use the following installation steps:

1.  Download [Anaconda](https://www.anaconda.com/download). We recommend downloading Anaconda’s latest Python 3 version (currently Python 3.7).
2.  Install the version of Anaconda which you downloaded, following the instructions on the download page.
3.  Congratulations, you have installed Jupyter Notebook. 

### Install the necessary libraries for this project

1. Open  **Anaconda Prompt (Anaconda3)**

![Anaconda Prompt](https://lh3.googleusercontent.com/XahuY708yONPnaU0sSWLuPT8LLT9krQZMmgJ-vrkDqRvPvgPjz_S7GbgwUsnlY6HoTxajkJeVFEp_QfIb6NMajDRtYdzEsdBMC9Pp6tvwYq6nIBhgvs8a0v6rdI5m_T-3EexBtzw5jiFz7HQ22Rp5nIJov62vwvhOrYxhByGV0oLBRLa8UZiOoBC3MtRKlSPkZ2O4s3JA3MZnNxVotTxvz3ibP3wQDa9CFDXe_j78KUMP5wov7zCoDeU7M24zQeX4VAVD1lO5-XT9HJlu2xu5_ZUM3HbFw986CNzgEe3x6kW8zyCp1le-s4kQBW_Evatp3aQQXnkV9wyHgsUGB781XTaRE3GgvybFqNqA_YvT6cGDfE414KhEE9az4ncgO3OYUesK9FEr4L-9ZnVcBEt9A2XZwjAnoxfMLtnJo6tK93gHlmomFyyeHBhrJMR2qlKZyHL3imRAgaP7D-tTcm2oCNA5Lhr4gLdp_32mqbfLreRckv7UC8urORnq2gDDcC5yhfw2U07e4q5lpB9XSB7eQoojfLWvZG8Ftnb_ebq9EYWuU9QEr6f0cnBGaDySSvW-Oj3_gvISMv2XkBcuioN6vFaI1Iu8hHbEd5ugHBBJbE-nR2soCJtwe-jbfqSlKbWmCGM6avldlf1TEpnLLMa3e3xzdMywCRErhU8yUEaW1tiZZO-nag09qbnhk22=w322-h257-no)

2. Type command: `pip install beautifulsoup4 python-docx openpyxl`

![Command](https://lh3.googleusercontent.com/MvxHNJJg4E1hfk6a2S16tvEINarxIEA2pnLvOQpfuqoFgEvbY28mCRRWRZOW_9EW9svDeulq0tUapAb9IXXf2nocyxEWVo78O2Jb9x2pJmV4RGVZJ2wRX0ktdxfHtIaFI0daunpxf9BQFmqK3_nEvM_AYQkHaQi2eg-IqKvBkJyJWZtciPu-Bn4dknJadO0YGOMzOmADxOrSe9CxE4B724MUw6Wutq7HQ-QzMrdXtpf1mHs6wLrQ-M4-H3iOMiKdHiCuWZsI_mpvDZATYAHr4-biV-_zr5SkCGiNBMJQRWupaJAlEKkUgTv3-3njCW2G6F0TMr5kR4QPAJTiclARE4bZucWa4vjT61fSUYtWhGbwozLDFUL5gt49RmFprABhdbhg_ahefFC9RovnCavgY1f3GJrHstykhK8M0iJXGKWo5dc76Of14xNXF2p7lOWxnBb1zVy-VK_c_GpSLiTL0mtI1aP-h3xAqh0XMICYlR3gxXGW1kJl58YpdlGBPv9pRb-Yx-5A4PTpxSMLC3256wZL4vqwM4FPzzCvINItfUlYZK7-b7Br1Iz2Pyo_5TVrUY8wOCww-cHGcV4bxI8_qiMRXFGSES3lziBNWBB9Ugf8jXbhfvbyvRZGVy5HNgWM6mxHW9sPScnxEIlqb1rwJ9hCP_sCVFNPMP7FK6vOuk2HVGxL1Yg0LxfUHhxT=w600-h112-no)

## Demonstration

### Starting Notebook Server
1. Download & extract the zip file provided.

![Script File](https://lh3.googleusercontent.com/VJwnIVIvsYz9-Or7p_IgaTV-mOdUH83jtVLzl6y-cbdYKnQvNJFtHwhiSzl89kMjdCGC5T0C37Ydx3N_9u7QcsazRLMmTwevVGyaBRv5j9LXVmw3Wif0hb4dWVtXQruVJ9mVgZPYs6R3qXuTnc7mpN5y4BVTI6yYssmoJ7GsdoAzL7KMXb27w_RxA7ODDpo79KK0pfpzeydc38CuQqWTJlWz_l2GrYh5i-fTTG8urFK4xsk-IODIZsihCXYZss0YFdLA8BFlV_EaG09ixnR_6z9y9ab6vc-5VVV2e1MIUSZiD5QjDj-g6dW7I82p0Mly_OyNEskRpIcBqY3DSkpFnlllg5GVHUEWnqZYy9SBiwPZPuM73LN9mMJ4Nw_aD7dEXcMTTkgERQ4_MGCbO8DvmaWgStlcPzoE4elSkYHn-ltvAKhr-dn2byu1ob8PGsbSJOeCf7GZkMSDHB8IMoMEG9yr-X3IAF2xhmggRuI3gGBmZNP-S5-3Gnb0ityOHFChd0JJWyc13s3vBdhYDQdV3YMQ_m8ya4NLXpLuBdGgsaKY4ZqjYCJv-oF6p7zeVMjuZTbPIPNpvXDAZOTEd9NQBRCQySzj5OICgVDfrJf1eMvLq0yGAwJej6ehnXzuvPds1FVD-dJalAwej44VvORJ95a02meTwo6g-ImYlW8PiuXScPypVjH70Vatae7o=w797-h114-no)

2. Open **Anaconda Prompt (Anaconda3)**  and run below commands

      2.a Change the directory to extracted folder using **cd** command.
    
      2.b Type below command to open  **Jupyter Notebook**
      
          `jupyter notebook`

![Jupyter](https://lh3.googleusercontent.com/IkC8V-ypEir1Qulf9BUPb1wIxlBN7t-M4a8wQXe5d9ly0gz_JhgSH86j9-O2gK5XE_dKiXkCqV5HjqJhTKl4Cz8rrLOWinywCFPFNgurRa_r9JQ9sxEbqfd2oGn6dlb4K9u_CcZE5W-7TjT77kmrQZPrrYnIaDS6k1a_10XGYpZc6rEIvzHcThWaTcg7QxoUegEjgquTniwR_1nSEQZBY8OD6ZsOOMo7wqW8qsoJUnjBKsze6qmuAvQQ3Ru83eCUDQ8fGoQYJ4lEG8nAJq0UVThMfg3EOtoBSNGKZR-6ehASdEq7PuECm0cp6UxTUMy4ywLToGd9_2sOsPTCGy-Fb3T35boNrN_BZcUSQC6rUPn_C1JlHi_euKRttxi2W-1EnqXiGIWmJ_TISqPKsZ9hos-5bv51Lo2sMP3KOTUq5Cor0iDbSEGEYsnI2X11mL8Sq_K74bGxKxynTjNMJrsfmvN2jFvdCGspKTLFm5HzMRIvvJFWx21t_j6usHD02hEbEMzLsWvnzajAoCEj8iQmlkDhDUD41TaSOuHGY90eKauHj5u65azcC-Syn1yqgMe94199pnsXMSFbxz0Fkr4X7TZ-v4DWlQsrfcBi3BzKlyXGmPlzwkR7S9MtGtKaxhd7j8TCkdxSFVBu3tQ8WEuV8xWAd8rkL_hW8hF_Dv27N985rj1F7GLM8qFoy9ii=w978-h159-no)

3.  This will print some information about the notebook server in your terminal, including the URL of the web application (by default, `http://localhost:8888`)

4. When the notebook opens in your default browser, you will see the **Notebook Dashboard** 
![Dashboard](https://lh3.googleusercontent.com/5HDH9xnhAL8rqqAQnvaSHqmAg00ygEkAotQO0UDXYVJL9nRWs2HxKiQh1IHfO9wE2Nmutk45-dUXtL_UtWWTmgBLTbALQmcX9wnnoJb7ZV-tGJ79-WhccCZWPWQYTVor7pZjqX8817VZIPr7jvcJk3wUcONxr05z-U80P3FhMbiS_8k4DIUxmRqO8bbnj4EbWKkmV3sCKVcWroSsVlYg0PKjdK6nbuwlwAmRS1jca--5hngtz_it3IiEJMXHaqEs1ExT7zuThYeZeJoCQks7C9t061bAbRO80ixRgWYn09kOkPoy8vtQr48TKchvUKS_o_32rZ5OGsZ4OKEE7sYQTjk3-DbkhkHlO1j8fup_Tx28aV9ulKka_fKArDxQlh4RLDEyWUjTix0PbokKPFxZFMK6CO1K3hJiZv7IGd4gO1KZyR1-fqmz6Iiiqs6X6rB4vkXxc7sBWqWlf2hkmh2SrLTkxVTf610DqKBBDyfMM1tjaITr1sgsWym7hJI92bxIYOYDoffdDNAY8koj8l1L2Ae-1-9p1q86di0iWTIsYWvrQF7qnZBnR4fXMDvww2jfJq-NKQerDaAxNdWcLsC2FHO0ncXSrjLhDqCvBmFzhRkw2rW4yEUBhK5DDi_lKxCnLqpgIqcDcBB3z8tKlLk4Exf0UqysCGPBQgrP5qSZwZDT7W0TOgttBOvnw7RH=w517-h318-no)

6. Open **PythonParseScript.ipynb** file


### Execution
To execute each cell in the script, press "Shift+Enter"

Cell 1: Make necessary imports.

![Import](https://lh3.googleusercontent.com/onTkpzkT_nbMq2aUvC_W3yxk0yWZ1Awvd-mTapvdm12AqhznIfgV67dmh0qbnV8CgFFS85tSMLcvciROojFtYcJCSB1jtHJ3EqSmaJVVu8gaN_sLM57QLsFgzGka6BmDYf9LSllx2TshfIFto3nUTJNF6ZMLd1-lDrE4DsEekqixqAj0guesbfmjQXuJjtbSUjy5hZPnxBf01vFwXbTyYGJterU35n2waXydjsOR6Zc9BBdN1v6Sht8oc8hfr752ncPB8TggYYDlp0qW8Tsk5JhmIuFR21vhTYd2a8o3QIo1EkeTYvSv6kbSI-LgtYX52pNYo7QZ-vBdcu2mwaDGbVS3zQce24w_srOAjDwGGUoyQW5yfQyBZwA-D7WP_WBIQbE6ZR95BD86gls-JxfZMA-zYZMOxlL1UcZLBZvVVlr_ea7tjYmdBkEtURlb7LeaO-sEq-suE-iybQwF9UciFMwXIlwno6q05CUh9lXodgY3JKUVtmyJiYFqWdf5orlxrnM6hD-2C5HqVsDMzearjPaqpfu-gs37UUEnUTkWWEvQtG8GS1QGVMke0pd-W-A4IoqZKHwtW-eaKiXL_z3tii-c2KLpukokjOZ8gx2az5v3xmi3zzayYd4Cl-TC3iUSZesBbWGmzPoVqSWH1naFcxWtgUEa89c3HvYyAaLMRYT2mPzvD9ameBxMwImU=w626-h312-no)

Cell 2: Function to return List of T-Codes from HTML file

![Return T-Codes from Html file](https://lh3.googleusercontent.com/GydBjDmnIKgoKch1vSuFmdrCMM5JN_Rg_iJ8TWcAgSOBL7xwGnm8uqeZfvUxdeOO5e9UAlzNE_rrt0FZK9fiyu-KGvj-sqcHtkbLFknkXkdbDGQhOKtm1G-0RKWIGF9qZkybF6_-mzd5Zmf4BrhxREmN3LIuCt5iuBaSZcci1Nz_v210wmes09rpCbIw-95qWooRz6YZvLc6PIHZo6HX83GHaBxHZESr__WVW3pbAcqkB5plUI2DG0MV5n4d0zPPkIjmOcxXAz0w9ilfQy9Tkux7aYaBWaTfbQuPqxR-AyloMY24SfUTLbDx4lFClIF-pT7OUUjPB7GPxLTBGkVi1pwfeHLlkKMZHnUfStXHHj_jXUtI5MMPNu3stmeW7jXUZVfq5qOMgmmbFl7zP54tSpE4C2dpGnk6EE333sZ6IHy1xqKdN0jJ1tmIkrmV61KFeCDGtc6E43XHicNPmdgbNsFvcb1igE6O--c1FMgAgrvh3GZ0csi45O6Bf79qWMLdEoFRPZJAAvgidWsy45Rsinzz5NopvpeU-j_PECbhcL87mBSm-LGAIHF5cwAFBX73FTq0GX9w0dL5ZYPUGLYXOnZWxdeuU-JuIO5HK794ORy-PFJ3PHiEIrHdsnR_0BAA8Qc9sX7ixKAsgrJ2mIjC5c6yUpiBBjN91ruPHz6mmmBEd26Zph3Yq-SEh91U=w677-h275-no)

Cell 3: Function to extract valid table from Docx file and append it to new Workbook

![Extract tables & create new sheet](https://lh3.googleusercontent.com/W_4IJSyCCR4S0PUvWZPklJmLnoePWn-GYKp4f1xsyNVNUJDzXcjbFLnqJNUFEgd1uP0FlJRuuDLgEzCH3OPEiMYUtcEh7KN-O57ZwJIgB0ojkG2NtLOj39ETZeBuMgAQfiEco1KL8NaW-W4zwpAkvOUbLYQo7lwTtQpnhsXoscj0uMdliMc1Rp1mOBi84G4ypla5YrNbUD6z3d7yhi2eDjAyd9PqEojHl-wYIeacu3zSj3E_zSc1f0yAk8ZPTAajw0u8Lhbd7jJhYKyhWE1HY-gyyQMXoxr29D-FB1gyqXNYqlKEAMsvHhyFSa2Vzofi8lJIzzAC6sxhawSnrExddPRoCHk95qkjs9sHY7H7mjOYsiQJF5zy5gWjTZ5gdIeK7l3rX3FC8c97cAAKfbpAXqLRx4NVqx5kAcleklxEtCgVdKWOuNTajnsXVbJQ_2CUtoUJdNQxcWffRWYiE_NGpELQNFVy5_zY5ZFt2kEU5PDwv1IA8WY95_bjKzWRFW4qoCQBtutWo8btEBAdMTp7noyL8MfbU1AL6SD2Voz_YsA-1q8xHTKtgj-P_5bU7q1Sr8Yd8cZGlYxdUeChfCyTTqEaGAVYFWVLFX2krO60_n568spfDQSe7DVvLlVKtEYd_3CJhQa-cZHEzHpfSiko0ihexEQIerYiNWTDGZNkVK6REoqsA3xVKDWIMeHA=w1011-h444-no)

Cell 4: Create new Workbook by calling previously defined functions.

**Note:** Before executing this cell, update the value for below mentioned variables (input_html_dir, input_docx_dir) to set input HTML & Docx file directory respectively.

   `input_html_dir = 'Accelerated Third-Party Returns.html'`
   
   `input_docx_dir = 'Accelerated Third-Party Returns.docx'`

![Main](https://lh3.googleusercontent.com/p7zydqdKRarpx0qjNOsqjOCb7zsphL8YloyQYShhUuxmoG2jTYjFU13FC9T61NWHd8EEu4whAB7GUz9Z4ljF8a-EHJa1BotV-jsKkJL7blBVSPZ6midD9q6XvLzo3iIrNYfmrzoV2NeIeowTgfPD-CnD0h4J2DlCMab1c7Q2GMq-k86Iqsgnd7VEExi3fWnNEwZV1AqVDiI5PnsD73vrRG1zY41Fa6RPYuvWz9MneNnZ6igcaJ9HqyE5Pz6iGWDp4Q1Kq_vr5bWtb9YQI-5-_JCxkcvLnEwRtgwY7tSGrQn0Dl59dxqTHqy2jHiO8DqxoQwl3CvkxCj9ZeCWvcBzh1Lw0g7sk6H9H0WqzDnXm6aI7Yo7duVRNZcLKrf61EGnBHB4pfOmFh60ItOe57XSQzDs6uWUMHaQZyz-meHrJuoB8r95UuCjcuoQCgsaMAN8wsDuIuLKcjUaMcradMhGfxK7rQQ-BMYJgNcDbYmMfQW3jW70gNCv09F-fY-4kQwK6VxeNcLyDR4zJXqtPAPv-BAGBI3s7lqy6QnpJvpg8jxgQl53g2kOBiCaIl6yguUkPsBcQJWBKF1EJ921epVwpm6fhyDg4NY5e8Ms40iuIlKDtcoSsTIgiSNS-GCjbQWMyLgtge7xJgmDxVRJ6-ilZumCwgwoCYly4kNPh-qLpAdoVb46JNgkM8oKrmLf=w1141-h475-no)

### New workbook will be created in CWD(Current Working Directory)

![](https://lh3.googleusercontent.com/v8sI15Ma9PnM1E4oFHEQnA4EtCMdHn9l2pXVpOVV5ZWM1ydl4_gRrW64zsfVajqibcQviFHgE69mFgJsQ3moSM4Nq6iYNzUfkHOsuguOwrPeob80F3N78pkXeF8Mkoi73Kp-oMOViMRBrmh6vPbSnVvJJU17nSRhoz8mOn7r9t8KDUzYDcwc8j1xBtC7-9S045t6kiH8nVAodWMDBGMWRYpfSSpy0n_uDhSCwvkq7sWYzRe8jG2jzNpeusLuXHlZBj4nRbvd3kaoxJUeDTl5GsvRqx_wM0wwkZL10_WZ6QgVCQKweedujmKQWDiN_slwa0R3PXp3x8WoA_ndZmmhwGAEyK7pFnFAc8iTn5VbVBMylsWkU_sp7Pzs0pKnX1Gpz9liy3BQX0kzfZ0KJymy2CoXZWN8LPlvx3ezQlgZs7CJY6JnFZgeK004gF6LXo_q8uzsWYYeeC8VMyuFI59xkBZq0aNmFNNnuFOH8qcpjYARnnF0SU4R5vzM1EqLpldRVixHO20IzeMIp34rOAY2cKLfxZxkqmFdsIJUL9Chg_LaM2Nk9RSJCB9Z_wlbjabsoKsEoXTLx_hoo18f13BeQKjoqZTW747hPM1w1P2LOcs5UVCS58zW7ai-nRKwrTl1XEHcLlqo8BP2JpFfRs2p7WikbEWEuH3qzaEGBzD83CefELg9kusUs4yO0EiN=w728-h109-no)![enter image description here](https://lh3.googleusercontent.com/NDGg3NCwqktA3HmLO-6jQe3FJDF7Tzii8xwHiRiS7Zue3sDHeHsV-F-Fh6Dwfws7QP53cU_3t_dANzsxNPTGvv01Ez6Z3_ZtbH25Oohc3kN0LmcPdfvbuZ2w5Nm3QQacCix4tOl6hB432oVLVy9JQYW_efVJ7IyAzPfoz6GCFxFYRXcAxoXAVo7HR4_tTxIK6XfGhVEGzQXaOQzLrPFxL1iQG1pOPDKhilsBDhxnBmo5y8XpS5I36gL3bJ83zm4daoTuCOqSPCuZqiV161RiX2ckma3EMCUytj18gyIEvaTXfBeOeB4L7IvWGwVM22iIWA4NbBM_cTSvk3yGnUZ5VJ3jbAASZ7P-on-JbogU6_DEUQUlh3bNEn-JM8wNTEYWiAlHbS9WjnfX7u20q8JEmcA7BHL0Rd49nrKQLtTEoKtlT_EXCz9InPyyf--qRwcK0r3V5cOfNtQMDBUbyiL9KubaT3zalfNpcTJIbXGno0vY2Nn9CE5-KoGUtVf9G-oRnPd5C6ywVVZw65ca4k5jDolgsdvOVWa7jdNMU96UmibIQNpOGkPkdT9rl6Jo5JGy-w-KV2-P0iCr60MYk1OiuGDM2gjr01_a1nL5tiw_f3MpWYYQlL4zMR4juGD6twhqca4GKR2YTYzT_osuljTWI3Tr_BYqKwJ6W7A2qZdNMvkjUbUeoWfgovRf3Pgo=w1366-h482-no)
