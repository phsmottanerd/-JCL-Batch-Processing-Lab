[readme_reeditado_para_github_com_anima_es_e_texto_verde_neon.md](https://github.com/user-attachments/files/33187183/readme_reeditado_para_github_com_anima_es_e_texto_verde_neon.md)
<div align="center">

<!-- ANIMATED HEADER SVG -->
<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 800 130" width="100%">
  <rect width="100%" height="100%" fill="#050805" rx="10" stroke="#00FF66" stroke-width="2"/>
  <style>
    .main-title { font-family: 'Courier New', monospace; font-weight: bold; fill: #00FF66; font-size: 28px; }
    .sub-title { font-family: 'Courier New', monospace; fill: #00CC55; font-size: 14px; letter-spacing: 3px; }
    @keyframes neonGlow {
      0%, 100% { opacity: 0.3; filter: drop-shadow(0 0 2px #00FF66); }
      50% { opacity: 1; filter: drop-shadow(0 0 10px #00FF66); }
    }
    .anim-glow { animation: neonGlow 2.5s infinite ease-in-out; }
  </style>
  <text x="50%" y="45%" text-anchor="middle" class="main-title">JCL BATCH PROCESSING LAB</text>
  <text x="50%" y="75%" text-anchor="middle" class="sub-title anim-glow">■ IBM z/OS MAINFRAME ENVIRONMENT ■</text>
</svg>

</div>

<p align="center">
  <img src="https://img.shields.io/badge/IBM-z%2FOS-00ff66?style=for-the-badge&labelColor=050805" alt="IBM z/OS">
  <img src="https://img.shields.io/badge/JCL-Batch-00ff66?style=for-the-badge&labelColor=050805" alt="JCL Batch">
  <img src="https://img.shields.io/badge/JES%2FSDSF-Monitoring-00ff66?style=for-the-badge&labelColor=050805" alt="JES SDSF">
  <img src="https://img.shields.io/badge/Status-Lab%20Completed-00ff66?style=for-the-badge&labelColor=050805" alt="Status">
</p>

```diff
+ Practical Mainframe laboratory focused on JCL batch processing in an IBM z/OS training environment.
+ 
+ The project demonstrates the complete learning workflow: writing JCL, submitting a batch job, receiving a JES job ID, and monitoring the job through SDSF.
+ 
+ MAINFRAME • JCL • BATCH • JES • SDSF • z/OS
```

---

<div align="center">

<!-- TITLE 01 SVG -->
<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 800 50" width="100%">
  <rect width="100%" height="100%" fill="#050805" rx="6" stroke="#00FF66" stroke-width="1.5"/>
  <style>
    .sec-head { font-family: 'Courier New', monospace; font-weight: bold; fill: #00FF66; font-size: 18px; }
    @keyframes pulseFade { 0%, 100% { opacity: 0.3; } 50% { opacity: 1; } }
    .pulse { animation: pulseFade 2.5s infinite ease-in-out; }
  </style>
  <text x="50%" y="62%" text-anchor="middle" class="sec-head pulse">> 01 — PROJECT OVERVIEW <</text>
</svg>

</div>

```diff
+ This repository documents a hands-on JCL Batch Processing Lab performed on an IBM z/OS environment.
+ 
+ The objective was not to create a large application, but to demonstrate the fundamental mechanics of a traditional Mainframe batch workflow using real z/OS tooling.
+ 
+ ENVIRONMENT DETAILS:
+ 
+ - Platform: IBM z/OS
+ 
+ - Access environment: IBM training lab / Skytap
+ 
+ - Interface: TSO / ISPF / IBM Personal Communications
+ 
+ - Batch language: JCL
+ 
+ - Job management: JES
+ 
+ - Monitoring: SDSF
+ 
+ - Utility used in the test: IEFBR14
```

---

<div align="center">

<!-- TITLE 02 SVG -->
<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 800 50" width="100%">
  <rect width="100%" height="100%" fill="#050805" rx="6" stroke="#00FF66" stroke-width="1.5"/>
  <style>
    .sec-head { font-family: 'Courier New', monospace; font-weight: bold; fill: #00FF66; font-size: 18px; }
    @keyframes pulseFade { 0%, 100% { opacity: 0.3; } 50% { opacity: 1; } }
    .pulse { animation: pulseFade 2.5s infinite ease-in-out; }
  </style>
  <text x="50%" y="62%" text-anchor="middle" class="sec-head pulse">> 02 — OBJECTIVES <</text>
</svg>

</div>

```diff
+ The laboratory was designed to practice and demonstrate:
+ 
+ - JOB statement — job definition
+ 
+ - EXEC statement — execution step
+ 
+ - DD statement — data definition
+ 
+ - SYSOUT=* — spool/output routing
+ 
+ - JCL member creation in an ISPF library
+ 
+ - Job submission from ISPF
+ 
+ - JES job identification
+ 
+ - Job monitoring through SDSF
+ 
+ - Recognition of a JCL processing error
+ 
+ This is intentionally a small, focused lab. Its value is the direct interaction with z/OS batch processing rather than the size of the code.
```

---

<div align="center">

<!-- TITLE 03 SVG -->
<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 800 50" width="100%">
  <rect width="100%" height="100%" fill="#050805" rx="6" stroke="#00FF66" stroke-width="1.5"/>
  <style>
    .sec-head { font-family: 'Courier New', monospace; font-weight: bold; fill: #00FF66; font-size: 18px; }
    @keyframes pulseFade { 0%, 100% { opacity: 0.3; } 50% { opacity: 1; } }
    .pulse { animation: pulseFade 2.5s infinite ease-in-out; }
  </style>
  <text x="50%" y="62%" text-anchor="middle" class="sec-head pulse">> 03 — BATCH FLOW <</text>
</svg>

</div>

```diff
+ ┌──────────────────┐
+ │      JCL01       │
+ │     ISPF Edit    │
+ └────────┬─────────┘
+          │ SUBMIT
+          ▼
+ ┌──────────────────┐
+ │       JES        │
+ │  Job processing  │
+ └────────┬─────────┘
+          │
+          ▼
+ ┌──────────────────┐
+ │      SDSF        │
+ │ Status / Output  │
+ └──────────────────┘
+ 
+ The practical flow was:
+ 
+ Create → Edit → Submit → Receive JOBID → Monitor → Analyze
```

---

<div align="center">

<!-- TITLE 04 SVG -->
<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 800 50" width="100%">
  <rect width="100%" height="100%" fill="#050805" rx="6" stroke="#00FF66" stroke-width="1.5"/>
  <style>
    .sec-head { font-family: 'Courier New', monospace; font-weight: bold; fill: #00FF66; font-size: 18px; }
    @keyframes pulseFade { 0%, 100% { opacity: 0.3; } 50% { opacity: 1; } }
    .pulse { animation: pulseFade 2.5s infinite ease-in-out; }
  </style>
  <text x="50%" y="62%" text-anchor="middle" class="sec-head pulse">> 04 — JCL STRUCTURE <</text>
</svg>

</div>

```diff
+ The laboratory member was:
+ 
+ TSOXA86.ES52.EXEC(JCL01)
+ 
+ The JCL used for the first execution attempt was:
+ 
+ //JCL01    JOB CLASS=A,MSGCLASS=X
+ //STEP01   EXEC PGM=IEFBR14
+ //SYSPRINT DD SYSOUT=*
+ //SYSOUT   DD SYSOUT=*
+ 
+ LINE-BY-LINE BREAKDOWN:
+ 
+ - JOB           : Defines the batch job
+ 
+ - EXEC          : Defines the program/step to execute
+ 
+ - PGM=IEFBR14   : Calls the IBM utility used for a simple execution test
+ 
+ - DD            : Defines data/output resources for the step
+ 
+ - SYSOUT=*      : Sends output to the JES spool
```

---

<div align="center">

<!-- TITLE 05 SVG -->
<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 800 50" width="100%">
  <rect width="100%" height="100%" fill="#050805" rx="6" stroke="#00FF66" stroke-width="1.5"/>
  <style>
    .sec-head { font-family: 'Courier New', monospace; font-weight: bold; fill: #00FF66; font-size: 18px; }
    @keyframes pulseFade { 0%, 100% { opacity: 0.3; } 50% { opacity: 1; } }
    .pulse { animation: pulseFade 2.5s infinite ease-in-out; }
  </style>
  <text x="50%" y="62%" text-anchor="middle" class="sec-head pulse">> 05 — EXECUTION & MONITORING <</text>
</svg>

</div>

```diff
+ The job was submitted from the ISPF editor.
+ 
+ The z/OS environment generated:
+ 
+ JOB TSOXA861(JOB46704) SUBMITTED
+ 
+ The job was then located through:
+ 
+ SDSF ST
+ 
+ The status display showed:
+ 
+ TSOXA861  JOB46704
+ 
+ The job subsequently ended with:
+ 
+ JOB46704 $HASP165 TSOXA861 ENDED AT ESSMVS1 - JCL ERROR CN(INTERNAL)
+ 
+ IMPORTANT NOTE:
+ 
+ This repository does not claim a successful batch completion.
+ 
+ The lab successfully demonstrated JCL creation, submission, JES job identification and SDSF monitoring, while the execution attempt exposed a JCL processing error. That distinction is intentional and documented accurately.
+ 
+ For a portfolio project, this is preferable to presenting an unverified MAXCC=0000 as if it had occurred.
```

---

<div align="center">

<!-- TITLE 06 SVG -->
<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 800 50" width="100%">
  <rect width="100%" height="100%" fill="#050805" rx="6" stroke="#00FF66" stroke-width="1.5"/>
  <style>
    .sec-head { font-family: 'Courier New', monospace; font-weight: bold; fill: #00FF66; font-size: 18px; }
    @keyframes pulseFade { 0%, 100% { opacity: 0.3; } 50% { opacity: 1; } }
    .pulse { animation: pulseFade 2.5s infinite ease-in-out; }
  </style>
  <text x="50%" y="62%" text-anchor="middle" class="sec-head pulse">> 06 — LAB EVIDENCE <</text>
</svg>

</div>

```diff
+ Suggested evidence captured during the laboratory:
+ 
+ - IBM z/OS / TSO environment  -->  Mainframe lab access
+ 
+ - ISPF editor                 -->  JCL member creation
+ 
+ - JCL01 source                -->  JOB / EXEC / DD structure
+ 
+ - Submission message          -->  JES job creation
+ 
+ - JOB46704                    -->  Job identification
+ 
+ - SDSF Status Display         -->  Job monitoring
+ 
+ - JCL Error message           -->  Error detection / troubleshooting
```

---

<div align="center">

<!-- TITLE 07 SVG -->
<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 800 50" width="100%">
  <rect width="100%" height="100%" fill="#050805" rx="6" stroke="#00FF66" stroke-width="1.5"/>
  <style>
    .sec-head { font-family: 'Courier New', monospace; font-weight: bold; fill: #00FF66; font-size: 18px; }
    @keyframes pulseFade { 0%, 100% { opacity: 0.3; } 50% { opacity: 1; } }
    .pulse { animation: pulseFade 2.5s infinite ease-in-out; }
  </style>
  <text x="50%" y="62%" text-anchor="middle" class="sec-head pulse">> 07 — WHAT THIS DEMONSTRATES TO RECRUITERS <</text>
</svg>

</div>

```diff
+ This project is intentionally positioned as a hands-on Mainframe laboratory, not as a claim of production z/OS administration experience.
+ 
+ A recruiter reviewing this repository can quickly identify practical exposure to:
+ 
+ - IBM z/OS
+ 
+ - JCL
+ 
+ - Batch processing concepts
+ 
+ - JOB / EXEC / DD
+ 
+ - JES job submission
+ 
+ - SDSF monitoring
+ 
+ - ISPF
+ 
+ - Mainframe troubleshooting
+ 
+ - Understanding of the relationship between JCL, JES and batch execution
+ 
+ PROFESSIONAL POSITIONING:
+ 
+ "Hands-on laboratory experience with JCL batch processing in IBM z/OS, including ISPF editing, job submission, JES job identification and SDSF monitoring."
```

---

<div align="center">

<!-- TITLE 08 SVG -->
<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 800 50" width="100%">
  <rect width="100%" height="100%" fill="#050805" rx="6" stroke="#00FF66" stroke-width="1.5"/>
  <style>
    .sec-head { font-family: 'Courier New', monospace; font-weight: bold; fill: #00FF66; font-size: 18px; }
    @keyframes pulseFade { 0%, 100% { opacity: 0.3; } 50% { opacity: 1; } }
    .pulse { animation: pulseFade 2.5s infinite ease-in-out; }
  </style>
  <text x="50%" y="62%" text-anchor="middle" class="sec-head pulse">> 08 — NEXT STEPS <</text>
</svg>

</div>

```diff
+ Possible future iterations:
+ 
+ [ ] Correct and re-submit the JCL
+ 
+ [ ] Obtain a successful completion / return code
+ 
+ [ ] Add dataset allocation with DISP
+ 
+ [ ] Add a real input/output dataset
+ 
+ [ ] Expand the job to multiple EXEC steps
+ 
+ [ ] Document JES output in detail
+ 
+ [ ] Add additional SDSF evidence
```

---

<div align="center">

<!-- TITLE 09 SVG -->
<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 800 50" width="100%">
  <rect width="100%" height="100%" fill="#050805" rx="6" stroke="#00FF66" stroke-width="1.5"/>
  <style>
    .sec-head { font-family: 'Courier New', monospace; font-weight: bold; fill: #00FF66; font-size: 18px; }
    @keyframes pulseFade { 0%, 100% { opacity: 0.3; } 50% { opacity: 1; } }
    .pulse { animation: pulseFade 2.5s infinite ease-in-out; }
  </style>
  <text x="50%" y="62%" text-anchor="middle" class="sec-head pulse">> 09 — REPOSITORY STRUCTURE <</text>
</svg>

</div>

```diff
+ jcl-batch-processing-lab/
+ │
+ ├── README.md
+ ├── jcl/
+ │   └── JCL01.jcl
+ ├── docs/
+ │   └── projeto.md
+ ├── screenshots/
+ │   ├── 01-zos-environment.png
+ │   ├── 02-jcl-editor.png
+ │   ├── 03-job-submitted.png
+ │   ├── 04-sdsf-status.png
+ │   └── 05-jcl-error.png
+ └── assets/
+     ├── 01-title.svg
+     ├── 02-overview.svg
+     ├── 03-objectives.svg
+     ├── 04-architecture.svg
+     ├── 05-jcl.svg
+     ├── 06-execution.svg
+     ├── 07-evidence.svg
+     ├── 08-recruiters.svg
+     └── 09-future.svg
```

---

<div align="center">

<!-- TITLE 10 SVG -->
<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 800 50" width="100%">
  <rect width="100%" height="100%" fill="#050805" rx="6" stroke="#00FF66" stroke-width="1.5"/>
  <style>
    .sec-head { font-family: 'Courier New', monospace; font-weight: bold; fill: #00FF66; font-size: 18px; }
    @keyframes pulseFade { 0%, 100% { opacity: 0.3; } 50% { opacity: 1; } }
    .pulse { animation: pulseFade 2.5s infinite ease-in-out; }
  </style>
  <text x="50%" y="62%" text-anchor="middle" class="sec-head pulse">> 10 — AUTHOR <</text>
</svg>

</div>

```diff
+ Paulo Henrique Santana Motta
+ 
+ Mainframe • COBOL • Linux • JCL • Automation • Cybersecurity
+ 
+ Building practical projects that connect legacy systems, Mainframe technologies, Linux, automation and modern development.
```

---

<div align="center">

```diff
+ ╔══════════════════════════════════════════════════════════╗
+ ║  IBM z/OS  |  JCL  |  JES  |  SDSF  |  BATCH PROCESSING ║
+ ╚══════════════════════════════════════════════════════════╝
```

```diff
+ END OF LAB
```

</div>
