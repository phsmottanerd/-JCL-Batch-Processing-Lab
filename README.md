[readme_reeditado_estilo_mainframe_neon.md](https://github.com/user-attachments/files/33186798/readme_reeditado_estilo_mainframe_neon.md)
<div align="center">

<!-- MAIN ANIMATED TITLE SVG -->
<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 850 140" width="100%">
  <defs>
    <style>
      @keyframes pulseGlow {
        0% { opacity: 0.3; text-shadow: 0 0 5px #00FF66; }
        50% { opacity: 1; text-shadow: 0 0 15px #00FF66, 0 0 30px #00FF66, 0 0 45px #00CC55; }
        100% { opacity: 0.3; text-shadow: 0 0 5px #00FF66; }
      }
      @keyframes scanline {
        0% { transform: translateY(-100%); }
        100% { transform: translateY(100%); }
      }
      .main-title {
        fill: #00FF66;
        font-family: 'Courier New', monospace, monospace;
        font-weight: bold;
        font-size: 38px;
        animation: pulseGlow 3s infinite ease-in-out;
      }
      .sub-title {
        fill: #00CC55;
        font-family: 'Courier New', monospace, monospace;
        font-size: 16px;
        letter-spacing: 2px;
      }
      .bg-card {
        fill: #050B05;
        stroke: #00FF66;
        stroke-width: 2;
        rx: 10px;
      }
    </style>
  </defs>
  <rect width="100%" height="100%" class="bg-card" />
  <text x="50%" y="55" text-anchor="middle" class="main-title">JCL BATCH PROCESSING LAB</text>
  <text x="50%" y="95" text-anchor="middle" class="sub-title">[ IBM z/OS • JES • SDSF • ISPF ]</text>
</svg>

<p align="center">
  <img src="https://img.shields.io/badge/IBM-z%2FOS-00ff66?style=for-the-badge&labelColor=050805" alt="IBM z/OS">
  <img src="https://img.shields.io/badge/JCL-Batch-00ff66?style=for-the-badge&labelColor=050805" alt="JCL Batch">
  <img src="https://img.shields.io/badge/JES%2FSDSF-Monitoring-00ff66?style=for-the-badge&labelColor=050805" alt="JES SDSF">
  <img src="https://img.shields.io/badge/Status-Lab%20Completed-00ff66?style=for-the-badge&labelColor=050805" alt="Status">
</p>

<font color="#00FF66"><b>Practical Mainframe laboratory focused on JCL batch processing in an IBM z/OS training environment.</b><br>
<i>The project demonstrates the complete learning workflow: writing JCL, submitting a batch job, receiving a JES job ID, and monitoring the job through SDSF.</i></font>

<br><br>

<code><font color="#00FF66">MAINFRAME • JCL • BATCH • JES • SDSF • z/OS</font></code>

</div>

<hr stroke="#00FF66">

<!-- SECTION 01 -->
<br>
<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 800 60" width="100%">
  <defs>
    <style>
      @keyframes fadeInOut {
        0%, 100% { opacity: 0.2; }
        50% { opacity: 1; text-shadow: 0 0 12px #00FF66; }
      }
      .sec-title { fill: #00FF66; font-family: 'Courier New', monospace; font-size: 22px; font-weight: bold; animation: fadeInOut 4s infinite ease-in-out; }
    </style>
  </defs>
  <rect width="100%" height="100%" fill="#050B05" stroke="#00FF66" stroke-width="1" rx="5"/>
  <text x="20" y="38" class="sec-title">01 — PROJECT OVERVIEW</text>
</svg>

<font color="#00FF66">

<p>This repository documents a hands-on <b>JCL Batch Processing Lab</b> performed on an <b>IBM z/OS environment</b>.</p>
<p>The objective was not to create a large application, but to demonstrate the fundamental mechanics of a traditional Mainframe batch workflow using real z/OS tooling.</p>

<h3>Environment Details</h3>

<ul>
  <li><b>Platform:</b> IBM z/OS</li>
  <li><b>Access environment:</b> IBM training lab / Skytap</li>
  <li><b>Interface:</b> TSO / ISPF / IBM Personal Communications</li>
  <li><b>Batch language:</b> JCL</li>
  <li><b>Job management:</b> JES</li>
  <li><b>Monitoring:</b> SDSF</li>
  <li><b>Utility used in the test:</b> IEFBR14</li>
</ul>

</font>

<!-- SECTION 02 -->
<br>
<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 800 60" width="100%">
  <defs>
    <style>
      .sec-title-2 { fill: #00FF66; font-family: 'Courier New', monospace; font-size: 22px; font-weight: bold; animation: fadeInOut 4s infinite ease-in-out; animation-delay: 0.5s; }
    </style>
  </defs>
  <rect width="100%" height="100%" fill="#050B05" stroke="#00FF66" stroke-width="1" rx="5"/>
  <text x="20" y="38" class="sec-title-2">02 — OBJECTIVES</text>
</svg>

<font color="#00FF66">

<p>The laboratory was designed to practice and demonstrate:</p>

<ul>
  <li><code>JOB</code> statement — job definition</li>
  <li><code>EXEC</code> statement — execution step</li>
  <li><code>DD</code> statement — data definition</li>
  <li><code>SYSOUT=*</code> — spool/output routing</li>
  <li>JCL member creation in an ISPF library</li>
  <li>Job submission from ISPF</li>
  <li>JES job identification</li>
  <li>Job monitoring through SDSF</li>
  <li>Recognition of a JCL processing error</li>
</ul>

<p><i>This is intentionally a small, focused lab. Its value is the direct interaction with z/OS batch processing rather than the size of the code.</i></p>

</font>

<!-- SECTION 03 -->
<br>
<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 800 60" width="100%">
  <defs>
    <style>
      .sec-title-3 { fill: #00FF66; font-family: 'Courier New', monospace; font-size: 22px; font-weight: bold; animation: fadeInOut 4s infinite ease-in-out; animation-delay: 1s; }
    </style>
  </defs>
  <rect width="100%" height="100%" fill="#050B05" stroke="#00FF66" stroke-width="1" rx="5"/>
  <text x="20" y="38" class="sec-title-3">03 — BATCH FLOW</text>
</svg>

<font color="#00FF66">

```text
┌──────────────────┐
│      JCL01       │
│     ISPF Edit    │
└────────┬─────────┘
         │ SUBMIT
         ▼
┌──────────────────┐
│       JES        │
│  Job processing  │
└────────┬─────────┘
         │
         ▼
┌──────────────────┐
│      SDSF        │
│ Status / Output  │
└──────────────────┘
```

<p><b>The practical flow was:</b></p>
<p><code>Create</code> → <code>Edit</code> → <code>Submit</code> → <code>Receive JOBID</code> → <code>Monitor</code> → <code>Analyze</code></p>

</font>

<!-- SECTION 04 -->
<br>
<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 800 60" width="100%">
  <defs>
    <style>
      .sec-title-4 { fill: #00FF66; font-family: 'Courier New', monospace; font-size: 22px; font-weight: bold; animation: fadeInOut 4s infinite ease-in-out; animation-delay: 1.5s; }
    </style>
  </defs>
  <rect width="100%" height="100%" fill="#050B05" stroke="#00FF66" stroke-width="1" rx="5"/>
  <text x="20" y="38" class="sec-title-4">04 — JCL STRUCTURE</text>
</svg>

<font color="#00FF66">

<p>The laboratory member was:</p>
<p><code>TSOXA86.ES52.EXEC(JCL01)</code></p>

<p>The JCL used for the first execution attempt was:</p>

```jcl
//JCL01    JOB CLASS=A,MSGCLASS=X
//STEP01   EXEC PGM=IEFBR14
//SYSPRINT DD SYSOUT=*
//SYSOUT   DD SYSOUT=*
```

<h3>Line-by-Line Analysis</h3>

<table>
  <thead>
    <tr>
      <th><font color="#00FF66">Statement</font></th>
      <th><font color="#00FF66">Purpose</font></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><font color="#00FF66"><code>JOB</code></font></td>
      <td><font color="#00FF66">Defines the batch job</font></td>
    </tr>
    <tr>
      <td><font color="#00FF66"><code>EXEC</code></font></td>
      <td><font color="#00FF66">Defines the program/step to execute</font></td>
    </tr>
    <tr>
      <td><font color="#00FF66"><code>PGM=IEFBR14</code></font></td>
      <td><font color="#00FF66">Calls the IBM utility used for a simple execution test</font></td>
    </tr>
    <tr>
      <td><font color="#00FF66"><code>DD</code></font></td>
      <td><font color="#00FF66">Defines data/output resources for the step</font></td>
    </tr>
    <tr>
      <td><font color="#00FF66"><code>SYSOUT=*</code></font></td>
      <td><font color="#00FF66">Sends output to the JES spool</font></td>
    </tr>
  </tbody>
</table>

</font>

<!-- SECTION 05 -->
<br>
<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 800 60" width="100%">
  <defs>
    <style>
      .sec-title-5 { fill: #00FF66; font-family: 'Courier New', monospace; font-size: 22px; font-weight: bold; animation: fadeInOut 4s infinite ease-in-out; animation-delay: 2s; }
    </style>
  </defs>
  <rect width="100%" height="100%" fill="#050B05" stroke="#00FF66" stroke-width="1" rx="5"/>
  <text x="20" y="38" class="sec-title-5">05 — EXECUTION &amp; MONITORING</text>
</svg>

<font color="#00FF66">

<p>The job was submitted from the ISPF editor.</p>

<p>The z/OS environment generated:</p>
<pre><code>JOB TSOXA861(JOB46704) SUBMITTED</code></pre>

<p>The job was then located through:</p>
<pre><code>SDSF ST</code></pre>

<p>The status display showed:</p>
<pre><code>TSOXA861  JOB46704</code></pre>

<p>The job subsequently ended with:</p>
<pre><code>JOB46704 $HASP165 TSOXA861 ENDED AT ESSMVS1 - JCL ERROR CN(INTERNAL)</code></pre>

<h3>Important Note</h3>

<p><b>This repository does not claim a successful batch completion.</b></p>
<p>The lab successfully demonstrated <b>JCL creation, submission, JES job identification and SDSF monitoring</b>, while the execution attempt exposed a JCL processing error. That distinction is intentional and documented accurately.</p>
<p>For a portfolio project, this is preferable to presenting an unverified <code>MAXCC=0000</code> as if it had occurred.</p>

</font>

<!-- SECTION 06 -->
<br>
<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 800 60" width="100%">
  <defs>
    <style>
      .sec-title-6 { fill: #00FF66; font-family: 'Courier New', monospace; font-size: 22px; font-weight: bold; animation: fadeInOut 4s infinite ease-in-out; animation-delay: 2.5s; }
    </style>
  </defs>
  <rect width="100%" height="100%" fill="#050B05" stroke="#00FF66" stroke-width="1" rx="5"/>
  <text x="20" y="38" class="sec-title-6">06 — LAB EVIDENCE</text>
</svg>

<font color="#00FF66">

<p>Suggested evidence captured during the laboratory:</p>

<table>
  <thead>
    <tr>
      <th><font color="#00FF66">Evidence</font></th>
      <th><font color="#00FF66">Demonstrates</font></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><font color="#00FF66">IBM z/OS / TSO environment</font></td>
      <td><font color="#00FF66">Mainframe lab access</font></td>
    </tr>
    <tr>
      <td><font color="#00FF66">ISPF editor</font></td>
      <td><font color="#00FF66">JCL member creation</font></td>
    </tr>
    <tr>
      <td><font color="#00FF66">JCL01 source</font></td>
      <td><font color="#00FF66">JOB / EXEC / DD structure</font></td>
    </tr>
    <tr>
      <td><font color="#00FF66">Submission message</font></td>
      <td><font color="#00FF66">JES job creation</font></td>
    </tr>
    <tr>
      <td><font color="#00FF66">JOB46704</font></td>
      <td><font color="#00FF66">Job identification</font></td>
    </tr>
    <tr>
      <td><font color="#00FF66">SDSF Status Display</font></td>
      <td><font color="#00FF66">Job monitoring</font></td>
    </tr>
    <tr>
      <td><font color="#00FF66">JCL Error message</font></td>
      <td><font color="#00FF66">Error detection / troubleshooting</font></td>
    </tr>
  </tbody>
</table>

<p><i>Screenshots can be placed in <code>screenshots/</code> and linked here as the repository evidence is organized.</i></p>

</font>

<!-- SECTION 07 -->
<br>
<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 800 60" width="100%">
  <defs>
    <style>
      .sec-title-7 { fill: #00FF66; font-family: 'Courier New', monospace; font-size: 22px; font-weight: bold; animation: fadeInOut 4s infinite ease-in-out; animation-delay: 3s; }
    </style>
  </defs>
  <rect width="100%" height="100%" fill="#050B05" stroke="#00FF66" stroke-width="1" rx="5"/>
  <text x="20" y="38" class="sec-title-7">07 — WHAT THIS DEMONSTRATES</text>
</svg>

<font color="#00FF66">

<p>This project is intentionally positioned as a <b>hands-on Mainframe laboratory</b>, not as a claim of production z/OS administration experience.</p>

<p>A recruiter reviewing this repository can quickly identify practical exposure to:</p>

<ul>
  <li>IBM z/OS</li>
  <li>JCL</li>
  <li>Batch processing concepts</li>
  <li>JOB / EXEC / DD</li>
  <li>JES job submission</li>
  <li>SDSF monitoring</li>
  <li>ISPF</li>
  <li>Mainframe troubleshooting</li>
  <li>Understanding of the relationship between JCL, JES and batch execution</li>
</ul>

<h3>Professional Positioning</h3>

<blockquote>
  <font color="#00FF66"><b>"Hands-on laboratory experience with JCL batch processing in IBM z/OS, including ISPF editing, job submission, JES job identification and SDSF monitoring."</b></font>
</blockquote>

<p>This wording keeps the project technically relevant while remaining faithful to what was actually performed.</p>

</font>

<!-- SECTION 08 -->
<br>
<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 800 60" width="100%">
  <defs>
    <style>
      .sec-title-8 { fill: #00FF66; font-family: 'Courier New', monospace; font-size: 22px; font-weight: bold; animation: fadeInOut 4s infinite ease-in-out; animation-delay: 3.5s; }
    </style>
  </defs>
  <rect width="100%" height="100%" fill="#050B05" stroke="#00FF66" stroke-width="1" rx="5"/>
  <text x="20" y="38" class="sec-title-8">08 — NEXT STEPS</text>
</svg>

<font color="#00FF66">

<p>Possible future iterations:</p>

```text
[ ] Correct and re-submit the JCL
[ ] Obtain a successful completion / return code
[ ] Add dataset allocation with DISP
[ ] Add a real input/output dataset
[ ] Expand the job to multiple EXEC steps
[ ] Document JES output in detail
[ ] Add additional SDSF evidence
```

</font>

<!-- SECTION 09 -->
<br>
<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 800 60" width="100%">
  <defs>
    <style>
      .sec-title-9 { fill: #00FF66; font-family: 'Courier New', monospace; font-size: 22px; font-weight: bold; animation: fadeInOut 4s infinite ease-in-out; animation-delay: 4s; }
    </style>
  </defs>
  <rect width="100%" height="100%" fill="#050B05" stroke="#00FF66" stroke-width="1" rx="5"/>
  <text x="20" y="38" class="sec-title-9">09 — REPOSITORY STRUCTURE</text>
</svg>

<font color="#00FF66">

```text
jcl-batch-processing-lab/
│
├── README.md
├── jcl/
│   └── JCL01.jcl
├── docs/
│   └── projeto.md
├── screenshots/
│   ├── 01-zos-environment.png
│   ├── 02-jcl-editor.png
│   ├── 03-job-submitted.png
│   ├── 04-sdsf-status.png
│   └── 05-jcl-error.png
└── assets/
    ├── 01-title.svg
    ├── 02-overview.svg
    ├── 03-objectives.svg
    ├── 04-architecture.svg
    ├── 05-jcl.svg
    ├── 06-execution.svg
    ├── 07-evidence.svg
    ├── 08-recruiters.svg
    └── 09-future.svg
```

</font>

<!-- SECTION 10 -->
<br>
<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 800 60" width="100%">
  <defs>
    <style>
      .sec-title-10 { fill: #00FF66; font-family: 'Courier New', monospace; font-size: 22px; font-weight: bold; animation: fadeInOut 4s infinite ease-in-out; animation-delay: 4.5s; }
    </style>
  </defs>
  <rect width="100%" height="100%" fill="#050B05" stroke="#00FF66" stroke-width="1" rx="5"/>
  <text x="20" y="38" class="sec-title-10">10 — AUTHOR</text>
</svg>

<font color="#00FF66">

<p><b>Paulo Henrique Santana Motta</b></p>
<p><b>Mainframe • COBOL • Linux • JCL • Automation • Cybersecurity</b></p>

<blockquote>
  <font color="#00FF66">Building practical projects that connect legacy systems, Mainframe technologies, Linux, automation and modern development.</font>
</blockquote>

<div align="center">

```text
╔══════════════════════════════════════════════════════════╗
║  IBM z/OS  |  JCL  |  JES  |  SDSF  |  BATCH PROCESSING ║
╚══════════════════════════════════════════════════════════╝
```

<h3><font color="#00FF66">*** END OF LAB ***</font></h3>

</div>

</font>
