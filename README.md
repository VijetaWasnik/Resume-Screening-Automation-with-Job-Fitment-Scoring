<h1>Resume Screening and Fitment Scoring System</h1>

<p>This project is a web-based automated resume screening tool that processes resumes, extracts relevant information, and scores candidates based on a provided job description. It uses advanced language models to analyze resumes, extract skills, and generate a fitment score for each candidate, helping recruiters quickly identify top candidates.</p>

<h2>Table of Contents</h2>
<ul>
    <li><a href="#project-overview">Project Overview</a></li>
    <li><a href="#features">Features</a></li>
    <li><a href="#folder-structure">Folder Structure</a></li>
    <li><a href="#setup">Setup</a></li>
    <li><a href="#usage">Usage</a></li>
    <li><a href="#code-overview">Code Overview</a></li>
    <li><a href="#dependencies">Dependencies</a></li>
    <li><a href="#contributing">Contributing</a></li>
    <li><a href="#license">License</a></li>
</ul>

<h2 id="project-overview">Project Overview</h2>
<p>The tool processes resumes uploaded through a web interface, extracts key information such as skills, contact info, and experience, and evaluates each candidate's suitability based on a given job description. The processed data is saved in an Excel file and displayed in an HTML file for easy analysis.</p>

<h2 id="features">Features</h2>
<ul>
    <li><strong>PDF Text Extraction</strong>: Extracts text from PDF resumes.</li>
    <li><strong>Fitment Scoring</strong>: Analyzes resume content and scores candidates based on a provided job description.</li>
    <li><strong>Skill Extraction</strong>: Matches candidate skills against a list provided in an Excel file.</li>
    <li><strong>Web Interface</strong>: Users can upload resumes and view results on HTML pages.</li>
    <li><strong>Excel Output</strong>: Saves extracted data and scores in <code>processed_profiles.xlsx</code>.</li>
    <li><strong>LLM Used</strong>: The model phi3 from OllamaLLM is used for text processing and generating fitment scores</code>.</li>
</ul>

<h2 id="folder-structure">Folder Structure</h2>
<pre>
Resume-Screening-Automation-with-Job-Fitment-Scoring
│   README.md
│   requirements.txt          
│   app.py                    # Main web application
│   utils.py                  # Helper functions for text extraction and scoring
│   processed_profiles.xlsx   # Output Excel file with processed profiles
├── Data
│   ├── jobdesc.txt           # Text file with the job description
│   ├── skills.xlsx           # Excel file containing required skills
    ├── Resumes
        └── *.pdf             # Folder containing resume PDFs  
├── templates
│   ├── job_desc.html         # Web page to display the job description
│   ├── upload_resumes.html   # Web page for uploading resumes
│   └── selected_profiles.html# Web page showing selected profiles and scores 
</pre>

<h2 id="setup">Setup</h2>
<ol>
    <li><strong>Clone the repository</strong>:
        <pre><code>git clone https://github.com/VijetaWasnik/Resume-Screening-Automation-with-Job-Fitment-Scoring</code></pre>
    </li>
    <li><strong>Install dependencies</strong>:
        <pre><code>pip install -r requirements.txt</code></pre>
    </li>
    <li><strong>Directory Setup</strong>: Ensure you have the following files and folders in place:
        <ul>
            <li><code>resumes/</code> folder with PDF resumes for processing.</li>
            <li><code>jobdesc.txt</code> file with the job description.</li>
            <li><code>skills.xlsx</code> file listing the required skills.</li>
        </ul>
    </li>
</ol>

<h2 id="usage">Usage</h2>
<ol>
    <li><strong>Start the Application</strong>:
        <pre><code>python app.py</code></pre>
    </li>
    <li><strong>Web Interface</strong>:
        <ul>
            <li>Open your browser and go to <code>http://localhost:5000</code>.</li>
            <li><strong>Upload Resumes</strong>: Use the <code>upload_resumes.html</code> page to upload resumes.</li>
            <li><strong>Job Description</strong>: View the job description on the <code>job_desc.html</code> page.</li>
            <li><strong>Results</strong>: View selected profiles and scores on the <code>selected_profiles.html</code> page.</li>
        </ul>
    </li>
    <li><strong>Excel Output</strong>: The application saves processed data in <code>processed_profiles.xlsx</code>, with columns such as:
        <ul>
            <li><strong>Filename</strong>: Name of the processed resume file.</li>
            <li><strong>Name</strong>: Extracted candidate name.</li>
            <li><strong>Location</strong>: Candidate's location.</li>
            <li><strong>Phone</strong>: Contact number.</li>
            <li><strong>Skills</strong>: Relevant skills extracted from the resume.</li>
            <li><strong>Experience</strong>: Years of experience.</li>
            <li><strong>Fitment Score</strong>: Calculated fitment score based on the job description.</li>
        </ul>
    </li>
</ol>

<h2 id = "code-overview">Code Overview</h2>
<ul>
    <li>
        <strong>pdfs_to_cleaned_and_extracted_excel</strong>: Main function that processes each resume, extracts key data, and generates a fitment score.
    </li>
    <li>
        <strong>extract_text_from_file</strong>: Utility to read and extract text from PDF files.
    </li>
    <li>
        <strong>fitment_summary_score</strong>: Uses the <code>phi3</code> model from <code>OllamaLLM</code> to compare the resume with the job description.
    </li>
    <li>
        <strong>LLM Model</strong>: The <code>phi3</code> model from <code>OllamaLLM</code> is used for natural language understanding and generating fitment summaries.
    </li>
</ul>


<h2 id="dependencies">Dependencies</h2>
<ul>
    <li>Python 3.x</li>
    <li>Required libraries: see <code>requirements.txt</code></li>
</ul>

<h2 id="contributing">Contributing</h2>
<p>Feel free to submit issues or pull requests to improve this project.</p>

<h2 id="license">License</h2>
<p>This project is licensed under the MIT License. See the LICENSE file for details.</p>

</body>
</html>
