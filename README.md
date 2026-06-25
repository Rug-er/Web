<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Ruger Group — Staff Portal</title>
  <link rel="stylesheet" href="css/style.css" />
</head>
<body>

<!-- ═══════════════════════════════════════════════════════════
     NAVBAR (hidden on login page via JS)
═══════════════════════════════════════════════════════════════ -->
<nav class="navbar" id="mainNavbar">
  <div class="navbar-brand">
    <span>&#9670;</span> Ruger Group
  </div>
  <div class="navbar-links" id="navLinks"></div>
  <div class="navbar-right" id="navRight"></div>
</nav>

<!-- ═══════════════════════════════════════════════════════════
     LOGIN PAGE
═══════════════════════════════════════════════════════════════ -->
<div id="login-page" class="page">
  <!-- Hide navbar on login -->
  <style>#login-page ~ * .navbar, #login-page.active ~ nav { display:none; }</style>
  <div class="login-wrapper">
    <div class="login-card">
      <div class="login-logo">
        <h2>&#9670; Ruger Group</h2>
        <p>Staff Portal — Please sign in to continue</p>
      </div>

      <div class="login-error" id="loginError"></div>

      <form onsubmit="handleLogin(event)">
        <div class="form-group">
          <label for="loginUser">Username</label>
          <input type="text" id="loginUser" placeholder="Enter your username" autocomplete="username" required />
        </div>
        <div class="form-group">
          <label for="loginPass">Password</label>
          <input type="password" id="loginPass" placeholder="Enter your password" autocomplete="current-password" required />
        </div>
        <button type="submit" class="btn btn-primary" style="width:100%;margin-top:.5rem">Sign In</button>
      </form>

      <div class="login-or">or</div>

      <button class="btn btn-outline" style="width:100%" onclick="continueAsGuest()">
        Continue as Guest
      </button>

      <p style="text-align:center;color:var(--gray-400);font-size:.8rem;margin-top:1.5rem">
        Guest access is read-only. Contact your admin to create an account.
      </p>
    </div>
  </div>
</div>

<!-- ═══════════════════════════════════════════════════════════
     MISSION PAGE
═══════════════════════════════════════════════════════════════ -->
<div id="mission-page" class="page">
  <div class="hero">
    <h1 id="missionHero">Our Mission</h1>
    <p id="missionSub"></p>
  </div>

  <div class="section">
    <p class="section-title">Why We Exist</p>
    <div class="divider"></div>
    <p style="color:var(--gray-600);font-size:1.05rem;margin-bottom:1.25rem" id="missionBody1"></p>
    <p style="color:var(--gray-600);font-size:1.05rem" id="missionBody2"></p>
  </div>

  <div style="background:var(--white);border-top:1px solid var(--blue-100);border-bottom:1px solid var(--blue-100)">
    <div class="section">
      <p class="section-title">Core Values</p>
      <p class="section-sub">The principles that guide every decision we make.</p>
      <div class="divider"></div>
      <div class="card-grid">
        <div class="card">
          <div class="card-icon">🎯</div>
          <h3 id="val1Title"></h3>
          <p id="val1Desc"></p>
        </div>
        <div class="card">
          <div class="card-icon">💡</div>
          <h3 id="val2Title"></h3>
          <p id="val2Desc"></p>
        </div>
        <div class="card">
          <div class="card-icon">🤝</div>
          <h3 id="val3Title"></h3>
          <p id="val3Desc"></p>
        </div>
        <div class="card">
          <div class="card-icon">⭐</div>
          <h3 id="val4Title"></h3>
          <p id="val4Desc"></p>
        </div>
      </div>
    </div>
  </div>
</div>

<!-- ═══════════════════════════════════════════════════════════
     ABOUT (DESCRIPTION) PAGE
═══════════════════════════════════════════════════════════════ -->
<div id="about-page" class="page">
  <div class="hero">
    <h1 id="aboutHero">About Us</h1>
    <p id="aboutSub"></p>
  </div>

  <div class="section">
    <p class="section-title">Who We Are</p>
    <div class="divider"></div>
    <p style="color:var(--gray-600);font-size:1.05rem;max-width:720px" id="aboutIntro"></p>
  </div>

  <!-- Stats bar -->
  <div style="background:linear-gradient(90deg,var(--blue-900),var(--blue-700));padding:2.5rem 2rem">
    <div style="max-width:900px;margin:0 auto;display:grid;grid-template-columns:repeat(auto-fit,minmax(160px,1fr));gap:2rem;text-align:center">
      <div>
        <div style="font-size:2.4rem;font-weight:800;color:var(--white)" id="stat1val"></div>
        <div style="color:var(--blue-300);font-size:.95rem" id="stat1lbl"></div>
      </div>
      <div>
        <div style="font-size:2.4rem;font-weight:800;color:var(--white)" id="stat2val"></div>
        <div style="color:var(--blue-300);font-size:.95rem" id="stat2lbl"></div>
      </div>
      <div>
        <div style="font-size:2.4rem;font-weight:800;color:var(--white)" id="stat3val"></div>
        <div style="color:var(--blue-300);font-size:.95rem" id="stat3lbl"></div>
      </div>
    </div>
  </div>

  <div style="background:var(--white);border-top:1px solid var(--blue-100);border-bottom:1px solid var(--blue-100)">
    <div class="section">
      <div style="display:grid;grid-template-columns:1fr 1fr;gap:3rem">
        <div>
          <h3 class="section-title" style="font-size:1.25rem" id="about2Title"></h3>
          <div class="divider"></div>
          <p style="color:var(--gray-600)" id="about2Body"></p>
        </div>
        <div>
          <h3 class="section-title" style="font-size:1.25rem" id="about3Title"></h3>
          <div class="divider"></div>
          <p style="color:var(--gray-600)" id="about3Body"></p>
        </div>
      </div>
    </div>
  </div>
</div>

<!-- ═══════════════════════════════════════════════════════════
     CAREERS PAGE
═══════════════════════════════════════════════════════════════ -->
<div id="careers-page" class="page">
  <div class="hero">
    <h1>Careers</h1>
    <p>Join a team that values your skills, your growth, and your future.</p>
    <button class="btn btn-outline" style="color:var(--white);border-color:rgba(255,255,255,.5)"
      onclick="document.getElementById('jobList').scrollIntoView({behavior:'smooth'})">
      View Open Positions ↓
    </button>
  </div>

  <div class="section">
    <p class="section-title">Why Work With Us</p>
    <p class="section-sub">We invest in our people as much as our projects.</p>
    <div class="divider"></div>
    <div class="card-grid">
      <div class="card">
        <div class="card-icon">🌱</div>
        <h3>Growth & Learning</h3>
        <p>Ongoing professional development, mentorship, and access to industry-leading resources.</p>
      </div>
      <div class="card">
        <div class="card-icon">🏡</div>
        <h3>Flexible Work</h3>
        <p>Remote, hybrid, and on-site options so you can work in the way that suits you best.</p>
      </div>
      <div class="card">
        <div class="card-icon">❤️</div>
        <h3>Great Benefits</h3>
        <p>Competitive compensation, health coverage, and a culture that celebrates your contributions.</p>
      </div>
    </div>
  </div>

  <div style="background:var(--white);border-top:1px solid var(--blue-100);padding:0 0 3rem">
    <div class="section" style="padding-bottom:0">
      <p class="section-title">Open Positions</p>
      <p class="section-sub">Find your next role. All positions are open until filled.</p>
      <div class="divider"></div>
    </div>
    <div style="max-width:1100px;margin:0 auto;padding:0 2rem">
      <div id="jobList"></div>
    </div>
  </div>
</div>

<!-- ═══════════════════════════════════════════════════════════
     POLICY PAGE
═══════════════════════════════════════════════════════════════ -->
<div id="policy-page" class="page">
  <div class="hero">
    <h1 id="policyHero">Company Policy</h1>
    <p id="policySub"></p>
  </div>

  <div class="section">
    <p style="color:var(--gray-400);font-size:.88rem;margin-bottom:2rem" id="policyUpdated"></p>

    <div class="policy-toc">
      <h4>Table of Contents</h4>
      <ol>
        <li><a href="#pol-conduct">Code of Conduct</a></li>
        <li><a href="#pol-privacy">Privacy & Data</a></li>
        <li><a href="#pol-attendance">Attendance & Hours</a></li>
        <li><a href="#pol-communication">Communication Standards</a></li>
        <li><a href="#pol-security">Information Security</a></li>
        <li><a href="#pol-harassment">Anti-Harassment</a></li>
      </ol>
    </div>

    <div class="policy-section" id="pol-conduct">
      <h3>1. Code of Conduct</h3>
      <p>All staff members are expected to conduct themselves in a professional, respectful, and ethical manner at all times. This applies to interactions with colleagues, clients, partners, and the public — whether in person, via email, or on digital platforms.</p>
      <p>Specific expectations include:</p>
      <ul>
        <li>Treating every individual with dignity and respect regardless of role or background.</li>
        <li>Representing the organization honestly and accurately in all communications.</li>
        <li>Avoiding conflicts of interest and disclosing any potential conflicts to management.</li>
        <li>Complying with all applicable laws and regulations.</li>
      </ul>
    </div>

    <div class="policy-section" id="pol-privacy">
      <h3>2. Privacy & Data</h3>
      <p>The organization is committed to protecting the personal information of employees, clients, and stakeholders. All staff handling personal data must do so in accordance with applicable data protection laws.</p>
      <ul>
        <li>Personal data must only be collected for legitimate, clearly defined purposes.</li>
        <li>Data must not be shared externally without appropriate authorization.</li>
        <li>Any suspected data breach must be reported to the IT department immediately.</li>
        <li>Employees must not access data beyond the scope of their role.</li>
      </ul>
    </div>

    <div class="policy-section" id="pol-attendance">
      <h3>3. Attendance & Hours</h3>
      <p>Regular, punctual attendance is essential to maintaining team productivity and client commitments. Staff are expected to adhere to their agreed-upon schedules and to communicate promptly in cases of absence.</p>
      <ul>
        <li>Absences must be reported to your direct supervisor as early as possible.</li>
        <li>Repeated unexcused absences may result in disciplinary action.</li>
        <li>Overtime requests must be pre-approved by management.</li>
        <li>Remote work arrangements are subject to individual employment agreements.</li>
      </ul>
    </div>

    <div class="policy-section" id="pol-communication">
      <h3>4. Communication Standards</h3>
      <p>Clear, professional communication is foundational to our work. All staff are expected to respond to internal and external messages in a timely manner and to maintain a constructive, solution-oriented tone.</p>
      <ul>
        <li>Internal emails and messages should be acknowledged within one business day.</li>
        <li>Client-facing communications must be reviewed for accuracy and tone before sending.</li>
        <li>Sensitive information should not be shared via unofficial channels.</li>
      </ul>
    </div>

    <div class="policy-section" id="pol-security">
      <h3>5. Information Security</h3>
      <p>Protecting company systems and information is a shared responsibility. Every employee plays a role in maintaining the integrity of our digital infrastructure.</p>
      <ul>
        <li>Strong, unique passwords must be used for all company accounts.</li>
        <li>Credentials must never be shared with other employees or third parties.</li>
        <li>Suspicious emails, links, or activities must be reported to IT immediately.</li>
        <li>Company devices must not be used for unauthorized personal activities.</li>
        <li>All software installed on company equipment must be approved by IT.</li>
      </ul>
    </div>

    <div class="policy-section" id="pol-harassment">
      <h3>6. Anti-Harassment Policy</h3>
      <p>We are committed to maintaining a workplace free from harassment, discrimination, and bullying of any kind. This applies to all employees, contractors, and visitors.</p>
      <p>Prohibited conduct includes but is not limited to:</p>
      <ul>
        <li>Verbal or written harassment based on race, gender, religion, age, disability, or other protected characteristics.</li>
        <li>Unwanted physical contact or threats.</li>
        <li>Creating or distributing offensive or inappropriate content in the workplace.</li>
        <li>Retaliating against any person who reports harassment in good faith.</li>
      </ul>
      <p>Any incidents should be reported to HR or a trusted manager. All complaints will be investigated promptly and confidentially.</p>
    </div>
  </div>
</div>

<!-- ═══════════════════════════════════════════════════════════
     ADMIN PAGE
═══════════════════════════════════════════════════════════════ -->
<div id="admin-page" class="page">
  <div class="admin-hero">
    <div style="font-size:2rem">⚙️</div>
    <div>
      <h2>Admin Panel</h2>
      <p>Manage accounts, edit site content, and configure job listings.</p>
    </div>
  </div>

  <div class="admin-tabs">
    <div class="admin-tab active" data-tab="accounts" onclick="switchAdminTab('accounts')">👥 Accounts</div>
    <div class="admin-tab" data-tab="content"  onclick="switchAdminTab('content')">✏️ Content</div>
    <div class="admin-tab" data-tab="jobs"     onclick="switchAdminTab('jobs')">💼 Jobs</div>
  </div>

  <!-- ACCOUNTS TAB -->
  <div class="admin-content">
    <div id="admin-accounts" class="admin-section">
      <div style="display:flex;align-items:center;justify-content:space-between;margin-bottom:1rem">
        <h3 style="margin:0">Staff Accounts</h3>
        <button class="btn btn-primary btn-sm" onclick="openCreateAccount()">+ Create Account</button>
      </div>
      <table class="data-table">
        <thead>
          <tr>
            <th>Username</th><th>Role</th><th>Created</th><th>Actions</th>
          </tr>
        </thead>
        <tbody id="accountTableBody"></tbody>
      </table>
    </div>

    <!-- CONTENT TAB -->
    <div id="admin-content" class="admin-section">
      <h3>Edit Site Content</h3>
      <p style="color:var(--gray-600);font-size:.93rem;margin-bottom:2rem">Changes are saved to this browser and reflected immediately across all pages.</p>

      <!-- Mission -->
      <div style="background:var(--blue-50);border:1px solid var(--blue-100);border-radius:var(--radius);padding:1.5rem;margin-bottom:1.5rem">
        <h4 style="color:var(--blue-900);margin-bottom:1rem;font-size:1rem">📋 Mission Page</h4>
        <div class="edit-field"><label>Hero Title</label><input id="ce-missionHero" type="text" /></div>
        <div class="edit-field"><label>Hero Subtitle</label><input id="ce-missionSub" type="text" /></div>
        <div class="edit-field"><label>Body Paragraph 1</label><textarea id="ce-missionBody1"></textarea></div>
        <div class="edit-field"><label>Body Paragraph 2</label><textarea id="ce-missionBody2"></textarea></div>
        <div class="form-row">
          <div class="edit-field"><label>Value 1 Title</label><input id="ce-val1" type="text" /></div>
          <div class="edit-field"><label>Value 1 Description</label><input id="ce-val1d" type="text" /></div>
        </div>
        <div class="form-row">
          <div class="edit-field"><label>Value 2 Title</label><input id="ce-val2" type="text" /></div>
          <div class="edit-field"><label>Value 2 Description</label><input id="ce-val2d" type="text" /></div>
        </div>
        <div class="form-row">
          <div class="edit-field"><label>Value 3 Title</label><input id="ce-val3" type="text" /></div>
          <div class="edit-field"><label>Value 3 Description</label><input id="ce-val3d" type="text" /></div>
        </div>
        <div class="form-row">
          <div class="edit-field"><label>Value 4 Title</label><input id="ce-val4" type="text" /></div>
          <div class="edit-field"><label>Value 4 Description</label><input id="ce-val4d" type="text" /></div>
        </div>
      </div>

      <!-- About -->
      <div style="background:var(--blue-50);border:1px solid var(--blue-100);border-radius:var(--radius);padding:1.5rem;margin-bottom:1.5rem">
        <h4 style="color:var(--blue-900);margin-bottom:1rem;font-size:1rem">ℹ️ About Page</h4>
        <div class="edit-field"><label>Hero Title</label><input id="ce-aboutHero" type="text" /></div>
        <div class="edit-field"><label>Hero Subtitle</label><input id="ce-aboutSub" type="text" /></div>
        <div class="edit-field"><label>Intro Paragraph</label><textarea id="ce-aboutIntro"></textarea></div>
        <div class="form-row">
          <div class="edit-field"><label>Section 2 Title</label><input id="ce-s2title" type="text" /></div>
          <div class="edit-field"><label>Section 3 Title</label><input id="ce-s3title" type="text" /></div>
        </div>
        <div class="form-row">
          <div class="edit-field"><label>Section 2 Body</label><textarea id="ce-s2body"></textarea></div>
          <div class="edit-field"><label>Section 3 Body</label><textarea id="ce-s3body"></textarea></div>
        </div>
        <div style="display:grid;grid-template-columns:repeat(3,1fr);gap:1rem">
          <div>
            <div class="edit-field"><label>Stat 1 Value</label><input id="ce-stat1" type="text" /></div>
            <div class="edit-field"><label>Stat 1 Label</label><input id="ce-stat1l" type="text" /></div>
          </div>
          <div>
            <div class="edit-field"><label>Stat 2 Value</label><input id="ce-stat2" type="text" /></div>
            <div class="edit-field"><label>Stat 2 Label</label><input id="ce-stat2l" type="text" /></div>
          </div>
          <div>
            <div class="edit-field"><label>Stat 3 Value</label><input id="ce-stat3" type="text" /></div>
            <div class="edit-field"><label>Stat 3 Label</label><input id="ce-stat3l" type="text" /></div>
          </div>
        </div>
      </div>

      <!-- Policy meta -->
      <div style="background:var(--blue-50);border:1px solid var(--blue-100);border-radius:var(--radius);padding:1.5rem;margin-bottom:1.5rem">
        <h4 style="color:var(--blue-900);margin-bottom:1rem;font-size:1rem">📜 Policy Page</h4>
        <div class="edit-field"><label>Hero Title</label><input id="ce-policyHero" type="text" /></div>
        <div class="edit-field"><label>Hero Subtitle</label><input id="ce-policySub" type="text" /></div>
        <div class="edit-field"><label>Last Updated Text</label><input id="ce-policyUpdated" type="text" /></div>
      </div>

      <button class="btn btn-success" onclick="saveContent()">💾 Save All Changes</button>
    </div>

    <!-- JOBS TAB -->
    <div id="admin-jobs" class="admin-section">
      <h3>Job Listings</h3>
      <div id="adminJobList"></div>

      <div style="background:var(--blue-50);border:1px solid var(--blue-100);border-radius:var(--radius);padding:1.5rem;margin-top:2rem" id="jobForm">
        <h4 style="color:var(--blue-900);margin-bottom:1rem;font-size:1rem" id="jobFormTitle">Add New Position</h4>
        <div class="form-row">
          <div class="edit-field"><label>Job Title</label><input id="jTitle" type="text" placeholder="e.g. Senior Engineer" /></div>
          <div class="edit-field"><label>Department</label><input id="jDept" type="text" placeholder="e.g. Engineering" /></div>
        </div>
        <div class="form-row">
          <div class="edit-field">
            <label>Type</label>
            <select id="jType">
              <option>Full-time</option>
              <option>Part-time</option>
              <option>Contract</option>
              <option>Internship</option>
            </select>
          </div>
          <div class="edit-field">
            <label>Location</label>
            <select id="jLocation">
              <option>Remote</option>
              <option>Hybrid</option>
              <option>On-site</option>
            </select>
          </div>
        </div>
        <div class="edit-field"><label>Description</label><textarea id="jDesc" placeholder="Brief description of the role..."></textarea></div>
        <div style="display:flex;gap:.75rem">
          <button class="btn btn-success" onclick="saveJob()">💾 Save Position</button>
          <button class="btn btn-outline"  onclick="clearJobForm()">✕ Cancel</button>
        </div>
      </div>
    </div>
  </div><!-- /admin-content -->
</div>

<!-- ═══════════════════════════════════════════════════════════
     ACCOUNT MODAL
═══════════════════════════════════════════════════════════════ -->
<div id="accountModal" style="display:none;position:fixed;inset:0;z-index:500;background:rgba(0,0,0,.45);align-items:center;justify-content:center;">
  <div style="background:var(--white);border-radius:14px;box-shadow:0 20px 60px rgba(0,0,0,.25);padding:2rem;width:100%;max-width:440px;margin:1rem">
    <div style="display:flex;align-items:center;justify-content:space-between;margin-bottom:1.5rem">
      <h3 id="accountModalTitle" style="color:var(--blue-900)">Create Account</h3>
      <button onclick="closeAccountModal()" style="background:none;border:none;font-size:1.4rem;cursor:pointer;color:var(--gray-400)">✕</button>
    </div>
    <input type="hidden" id="accEditIndex" />
    <div class="form-group">
      <label>Username</label>
      <input type="text" id="newAccUser" placeholder="Enter username" />
    </div>
    <div class="form-group">
      <label>Password</label>
      <input type="password" id="newAccPass" placeholder="Enter password" />
    </div>
    <div class="form-group">
      <label>Role</label>
      <select id="newAccRole">
        <option value="staff">Staff</option>
        <option value="admin">Admin</option>
      </select>
    </div>
    <div style="display:flex;gap:.75rem;margin-top:1.25rem">
      <button class="btn btn-primary" onclick="saveAccount()">Save Account</button>
      <button class="btn btn-outline" onclick="closeAccountModal()">Cancel</button>
    </div>
  </div>
</div>

<!-- ═══════════════════════════════════════════════════════════
     FOOTER
═══════════════════════════════════════════════════════════════ -->
<footer id="mainFooter">
  &copy; 2025 Ruger Group. All rights reserved. &nbsp;|&nbsp;
  <a href="#" onclick="nav('policy-page')">Policy</a> &nbsp;|&nbsp;
  <a href="#" onclick="nav('careers-page')">Careers</a>
</footer>

<!-- TOAST -->
<div class="toast" id="toast"></div>

<!-- ═══════════════════════════════════════════════════════════
     NAVBAR VISIBILITY LOGIC
═══════════════════════════════════════════════════════════════ -->
<script>
  // Watch for active page changes to toggle navbar/footer
  const observer = new MutationObserver(() => {
    const isLogin = document.getElementById('login-page').classList.contains('active');
    document.getElementById('mainNavbar').style.display = isLogin ? 'none' : '';
    document.getElementById('mainFooter').style.display = isLogin ? 'none' : '';
  });
  observer.observe(document.body, { subtree: true, attributeFilter: ['class'] });
</script>

<script src="js/app.js"></script>
</body>
</html>
