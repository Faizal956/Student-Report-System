<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Student Record System — Full UI + Marks</title>

    <!-- External libs -->
    <script src="https://cdn.jsdelivr.net/npm/chart.js"></script>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/jspdf/2.5.1/jspdf.umd.min.js"></script>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/html2canvas/1.4.1/html2canvas.min.js"></script>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/xlsx/0.18.5/xlsx.full.min.js"></script>

    <style>
        @import url('https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;600&display=swap');
        :root{
            --glass: rgba(255,255,255,0.12);
            --accent: #00f0ff;
            --accent-2: #7a00ff;
            --bg1: linear-gradient(120deg,#070724 0%, #1f0753 50%, #0b3d91 100%);
            --neon: drop-shadow(0 0 8px rgba(0,240,255,0.6));
            --glass-border: rgba(255,255,255,0.18);
        }
        *{box-sizing:border-box}
        body{
            margin:0; font-family:Poppins,system-ui,Arial; min-height:100vh; color:#e9f7ff;
            background: radial-gradient(circle at 10% 10%, rgba(122,0,255,0.10), transparent 10%),
                        radial-gradient(circle at 90% 90%, rgba(0,240,255,0.06), transparent 10%),
                        var(--bg1);
            transition: background 0.6s ease, color 0.4s;
        }

        /* Preloader */
        #preloader{position:fixed; inset:0; background:rgba(0,0,0,0.6); display:flex; align-items:center; justify-content:center; z-index:9999; color:#fff; flex-direction:column}
        #preloader .spinner{width:72px; height:72px; border-radius:50%; border:8px solid rgba(255,255,255,0.08); border-top-color:var(--accent); animation:spin 1s linear infinite}
        @keyframes spin{to{transform:rotate(360deg)}}

        /* Top frosted navbar */
        .topbar{position:fixed; top:0; left:0; right:0; height:64px; display:flex; align-items:center; gap:12px; padding:0 18px; background: rgba(255,255,255,0.06); backdrop-filter: blur(8px) saturate(140%); border-bottom: 1px solid rgba(255,255,255,0.06); z-index:50}
        .brand{display:flex; align-items:center; gap:12px}
        .logo{width:44px; height:44px; border-radius:10px; background:linear-gradient(45deg,var(--accent),var(--accent-2)); box-shadow:0 6px 18px rgba(122,0,255,0.18); display:flex;align-items:center;justify-content:center; font-weight:700}
        .app-title{font-weight:600; letter-spacing:0.2px}

        /* layout */
        .layout{display:flex; gap:20px; padding:86px 24px 40px}

        /* side menu */
        .side{width:260px; min-height:calc(100vh - 86px); position:relative}
        .side .menu{position:sticky; top:86px; display:flex; flex-direction:column; gap:12px}
        .card{background:var(--glass); border-radius:14px; padding:16px; border:1px solid var(--glass-border); box-shadow: 0 8px 30px rgba(0,0,0,0.35); transition: transform .35s ease, box-shadow .35s ease}
        .card:hover{transform:translateY(-6px)}
        .menu button{display:flex; align-items:center; gap:10px; padding:12px 14px; background:transparent; border:none; color:inherit; cursor:pointer; border-radius:10px; font-weight:600}
        .menu button:hover{background:linear-gradient(90deg, rgba(0,240,255,0.06), rgba(122,0,255,0.04)); box-shadow:var(--neon)}

        /* main area */
        .main{flex:1}

        /* pages (simple SPA) */
        .page{display:none; opacity:0; transform:translateY(12px); transition: all .45s ease}
        .page.active{display:block; opacity:1; transform:translateY(0)}

        /* large container */
        .panel{padding:18px; border-radius:14px}

        /* form */
        label{display:block; font-size:13px; margin-top:10px; color:rgba(255,255,255,0.9)}
        input[type=text], input[type=password], input[type=number]{width:100%; padding:12px; border-radius:10px; border:1px solid rgba(255,255,255,0.08); background: rgba(0,0,0,0.18); color:inherit; outline:none}
        input[type=text]:focus, input[type=password]:focus, input[type=number]:focus{box-shadow:0 0 18px rgba(0,240,255,0.12); border-color:var(--accent)}

        .row{display:flex; gap:12px}
        .col-2{flex:1}

        /* neon buttons */
        .neon-btn{padding:10px 14px; border-radius:10px; border:none; cursor:pointer; font-weight:700; background:linear-gradient(90deg,var(--accent),var(--accent-2)); color:#001; box-shadow:0 6px 20px rgba(0,240,255,0.12); transition:transform .18s}
        .neon-btn:hover{transform:translateY(-4px); filter:brightness(1.05); box-shadow:0 12px 40px rgba(0,240,255,0.2), 0 0 28px rgba(122,0,255,0.1)}

        /* switches & toggles */
        .toggle{display:inline-flex; align-items:center; gap:8px}
        .switch{width:48px; height:28px; background:rgba(255,255,255,0.09); border-radius:30px; position:relative; padding:4px; cursor:pointer}
        .switch .knob{width:20px; height:20px; background:#fff; border-radius:50%; position:absolute; left:4px; top:4px; transition:all .22s}
        .switch.on{background:linear-gradient(90deg,var(--accent),var(--accent-2)); box-shadow:var(--neon)}
        .switch.on .knob{left:24px}

        /* table */
        table{width:100%; border-collapse:collapse; margin-top:14px; overflow:hidden}
        th, td{padding:12px; text-align:left; font-size:14px}
        thead th{background:rgba(255,255,255,0.04); border-bottom:1px solid rgba(255,255,255,0.04)}
        tbody tr{border-bottom:1px dashed rgba(255,255,255,0.04)}
        tbody tr:hover{background:linear-gradient(90deg, rgba(0,240,255,0.02), rgba(122,0,255,0.01))}
        .highlight{background:linear-gradient(90deg, rgba(255,255,0,0.15), rgba(255,200,0,0.05))}

        /* small controls */
        .controls{display:flex; gap:8px; flex-wrap:wrap; margin-top:10px}
        .small{padding:8px 10px; border-radius:8px; border:1px solid rgba(255,255,255,0.06); background:transparent; color:inherit}

        /* animated counters */
        .stat-grid{display:flex; gap:12px; margin-top:12px}
        .stat{flex:1; padding:14px; border-radius:12px; background:linear-gradient(90deg, rgba(255,255,255,0.03), rgba(255,255,255,0.02)); text-align:center}
        .stat h2{font-size:28px; margin:6px 0}
        .stat p{margin:0; font-size:12px}

        /* profile */
        .avatar{width:86px; height:86px; border-radius:50%; background:rgba(255,255,255,0.08); display:flex; align-items:center; justify-content:center; font-weight:700}

        /* toast notifications */
        #toast{position:fixed; right:18px; bottom:18px; min-width:220px; padding:12px 16px; border-radius:10px; background:rgba(0,0,0,0.7); color:#fff; display:none; z-index:9999}

        /* login box */
        .login-wrap{display:flex; align-items:center; justify-content:center; height:calc(100vh - 86px)}
        .login-card{width:380px; max-width:92%; padding:28px; border-radius:14px; background:rgba(255,255,255,0.06); backdrop-filter: blur(10px); border:1px solid rgba(255,255,255,0.08); text-align:center; box-shadow:0 20px 60px rgba(0,0,0,0.5); transform:translateY(-20px); animation:floatIn .9s ease forwards}
        @keyframes floatIn{to{transform:none}}
        .login-card h2{margin:8px 0 18px}

        /* responsive */
        @media (max-width:900px){ .layout{flex-direction:column; padding:110px 16px 20px} .side{width:100%} .topbar{height:72px} }

        /* dark-mode advanced */
        .dark{ --bg1: linear-gradient(120deg,#020617 0%, #0b1833 50%, #03172a 100%); color:#dbeffd; filter:contrast(1.02) saturate(1.05) }
        .animate-theme{transition: background 0.8s cubic-bezier(.2,.9,.3,1), color .5s}

        /* tiny helpers */
        .muted{opacity:0.75; font-size:13px}
    </style>
</head>
<body class="animate-theme">

    <div id="preloader"><div class="spinner"></div><div style="margin-top:12px">Loading UI...</div></div>
    <div class="topbar">
        <div class="brand">
            <div class="logo">SR</div>
            <div>
                <div class="app-title">Student Record System</div>
                <div class="muted">Glass UI • Neon accents • Dashboard</div>
            </div>
        </div>
        <div style="flex:1"></div>
        <div style="display:flex; align-items:center; gap:12px">
            <div class="muted">Lang</div>
            <select id="langSelect" onchange="setLang(this.value)" class="small">
                <option value="en">EN</option>
                <option value="es">ES</option>
            </select>
            <div class="toggle">
                <div id="themeSwitch" class="switch" onclick="toggleTheme()"><div class="knob"></div></div>
            </div>
            <button id="profileBtn" class="small" onclick="navigateTo('profile')">Profile</button>
            <button class="small" onclick="navigateTo('login')">Logout</button>
        </div>
    </div>

    <div class="layout">
        <aside class="side">
            <div class="menu card">
                <button onclick="navigateTo('dashboard')">📊 Dashboard</button>
                <button onclick="navigateTo('records')">👥 Records</button>
                <button onclick="navigateTo('add')">➕ Add Record</button>
                <button onclick="navigateTo('profile')">🙍 Profile</button>
                <button onclick="navigateTo('settings')">⚙️ Settings</button>
                <div style="height:10px"></div>
                <div class="muted" style="font-size:13px">Export / Import</div>
                <div style="display:flex; gap:8px; margin-top:8px">
                    <button class="small" onclick="exportPDF()">Export PDF</button>
                    <button class="small" onclick="exportExcel()">Export Excel</button>
                </div>
            </div>
        </aside>

        <main class="main">
            <!-- LOGIN -->
            <section id="login" class="page">
                <div class="login-wrap">
                    <div class="login-card">
                        <h2 data-i18n="welcome">Welcome back</h2>
                        <p class="muted" data-i18n="signin">Sign in to access your student records</p>
                        <label data-i18n="role">Role</label>
                        <select id="loginRole" class="small"><option value="admin">Admin</option><option value="student">Student</option></select>
                        <label data-i18n="username">Username</label>
                        <input type="text" id="loginUser" placeholder="admin" value="admin">
                        <label data-i18n="password">Password</label>
                        <input type="password" id="loginPass" placeholder="password">
                        <div style="margin-top:12px; display:flex; gap:10px">
                            <button class="neon-btn" style="flex:1" onclick="doLogin()" data-i18n="signinBtn">Sign In</button>
                            <button class="small" onclick="navigateTo('dashboard')">Demo</button>
                        </div>
                    </div>
                </div>
            </section>

            <!-- DASHBOARD -->
            <section id="dashboard" class="page active">
                <div class="panel card">
                    <div style="display:flex; justify-content:space-between; align-items:center">
                        <h3 data-i18n="overview">Overview</h3>
                        <div class="muted">Total students: <span id="totalCount">0</span></div>
                    </div>
                    <div class="stat-grid">
                        <div class="stat"><p class="muted">Total Students</p><h2 id="statTotal">0</h2></div>
                        <div class="stat"><p class="muted">Avg Marks</p><h2 id="statAvg">0</h2></div>
                        <div class="stat"><p class="muted">Top Score</p><h2 id="statTop">0</h2></div>
                    </div>
                    <canvas id="courseChart" style="max-width:100%; margin-top:12px; height:220px"></canvas>
                </div>
            </section>

            <!-- RECORDS -->
            <section id="records" class="page">
                <div class="panel card">
                    <div style="display:flex; justify-content:space-between; align-items:center">
                        <h3 data-i18n="records">Student Records</h3>
                        <div>
                            <input type="text" id="searchBox" placeholder="Search by name, roll, course or marks" oninput="renderTable(true)" style="padding:8px; border-radius:8px; border:1px solid rgba(255,255,255,0.06)">
                        </div>
                    </div>

                    <div class="controls">
                        <button class="small" onclick="sortBy('name')">Sort: Name</button>
                        <button class="small" onclick="sortBy('roll')">Sort: Roll</button>
                        <button class="small" onclick="sortBy('marks')">Sort: Marks</button>
                        <button class="small" onclick="clearAll()" style="background:#7a002f">Clear All</button>
                        <button class="small" onclick="addDemoData()">Add Demo</button>
                    </div>

                    <div id="tableWrap" style="overflow:auto; max-height:420px; margin-top:12px">
                        <table id="studentTable">
                            <thead><tr><th>Name</th><th>Roll</th><th>Course</th><th>Marks</th><th>Grade</th><th>Actions</th></tr></thead>
                            <tbody></tbody>
                        </table>
                    </div>
                </div>
            </section>

            <!-- ADD / EDIT -->
            <section id="add" class="page">
                <div class="panel card">
                    <h3 id="formTitle">Add Student</h3>
                    <div style="max-width:720px">
                        <label>Name</label>
                        <input type="text" id="sName">
                        <label>Roll Number</label>
                        <input type="text" id="sRoll">
                        <label>Course</label>
                        <input type="text" id="sCourse">
                        <label>Total Marks (out of)</label>
                        <input type="number" id="sTotal" value="100">
                        <label>Marks Obtained</label>
                        <input type="number" id="sMarks" value="0">

                        <div style="display:flex; gap:10px; margin-top:12px">
                            <button class="neon-btn" onclick="saveRecord()" data-i18n="save">Save</button>
                            <button class="small" onclick="resetForm()">Reset</button>
                        </div>
                    </div>
                </div>
            </section>

            <!-- PROFILE -->
            <section id="profile" class="page">
                <div class="panel card">
                    <h3>Profile</h3>
                    <div style="display:flex; gap:14px; align-items:center">
                        <div>
                            <div id="avatarDisplay" class="avatar">A</div>
                            <input type="file" id="avatarUpload" accept="image/*" style="margin-top:8px" onchange="uploadAvatar(event)">
                        </div>
                        <div style="flex:1">
                            <label>Name</label>
                            <input type="text" id="profileName">
                            <label>Role</label>
                            <select id="profileRole" class="small"><option value="admin">Admin</option><option value="student">Student</option></select>
                            <div style="margin-top:12px"><button class="neon-btn" onclick="saveProfile()">Save Profile</button></div>
                        </div>
                    </div>
                </div>
            </section>

            <!-- SETTINGS -->
            <section id="settings" class="page">
                <div class="panel card">
                    <h3>Settings</h3>
                    <div style="display:flex; gap:14px; align-items:center; margin-top:10px; flex-wrap:wrap">
                        <div>
                            <div class="muted">Animated Dark Mode</div>
                            <div class="toggle" style="margin-top:6px">
                                <div id="animatedThemeSwitch" class="switch" onclick="toggleAnimatedTheme()"><div class="knob"></div></div>
                            </div>
                        </div>

                        <div>
                            <div class="muted">Neon Buttons</div>
                            <div style="margin-top:8px">
                                <button class="neon-btn">Try Neon</button>
                            </div>
                        </div>

                        <div>
                            <div class="muted">Theme Colors</div>
                            <div style="display:flex; gap:8px; margin-top:8px; align-items:center">
                                <input type="color" id="accentColor" value="#00f0ff"> <input type="color" id="accentColor2" value="#7a00ff"> <button class="small" onclick="applyThemeColors()">Apply</button>
                            </div>
                        </div>
                    </div>
                </div>
            </section>

        </main>
    </div>

    <div id="toast"></div>

    <script>
        // tiny i18n
        const i18n = {
            en: {
                welcome: 'Welcome back', signin: 'Sign in to access your student records', role: 'Role', username: 'Username', password: 'Password', signinBtn: 'Sign In', overview: 'Overview', records: 'Student Records', save: 'Save'
            },
            es: {
                welcome: 'Bienvenido', signin: 'Inicia sesión para acceder a tus registros', role: 'Rol', username: 'Usuario', password: 'Contraseña', signinBtn: 'Iniciar', overview: 'Resumen', records: 'Registros', save: 'Guardar'
            }
        };
        function setLang(l){ document.documentElement.lang=l; document.querySelectorAll('[data-i18n]').forEach(el=>{ const k=el.getAttribute('data-i18n'); el.innerText = i18n[l][k] || i18n['en'][k] || el.innerText; }); localStorage.setItem('lang', l); }

        // Basic SPA navigation + transitions
        function navigateTo(id){
            document.querySelectorAll('.page').forEach(p=>{p.classList.remove('active')});
            document.getElementById(id).classList.add('active');
            if(id==='dashboard') { renderChart(); animateStats(); }
            if(id==='records') renderTable(true);
            if(id==='profile') loadProfile();
        }

        // ----- Preloader -----
        window.addEventListener('load', ()=>{ setTimeout(()=>{ document.getElementById('preloader').style.display='none'; }, 600); });

        // ----- Authentication & roles -----
        function doLogin(){
            const role=document.getElementById('loginRole').value; const u=document.getElementById('loginUser').value; const p=document.getElementById('loginPass').value;
            // demo credentials: admin/admin or student/student
            if((role==='admin' && (u==='admin' && (p==='password' || p===''))) || (role==='student' && (u==='student' && (p==='student' || p==='')))){
                localStorage.setItem('srs_role', role); localStorage.setItem('srs_user', u); showToast('Logged in as '+role); navigateTo('dashboard');
            } else { showToast('Wrong credentials', true); }
        }

        // ----- Storage & records management (with marks) -----
        let students = JSON.parse(localStorage.getItem('students_v3') || '[]');
        let editIdx = -1;

        function saveRecord(){
            const name=document.getElementById('sName').value.trim();
            const roll=document.getElementById('sRoll').value.trim();
            const course=document.getElementById('sCourse').value.trim();
            const total=parseFloat(document.getElementById('sTotal').value)||100;
            const marks=parseFloat(document.getElementById('sMarks').value)||0;
            if(!name||!roll||!course){ showToast('Fill all fields', true); return; }
            const percent = Math.round((marks/total)*10000)/100; // two decimals
            const grade = getGrade(percent);
            const record = { name, roll, course, total, marks, percent, grade };
            if(editIdx>-1){ students[editIdx]=record; editIdx=-1; document.getElementById('formTitle').innerText='Add Student'; showToast('Record updated'); }
            else { students.push(record); showToast('Record added'); }
            persist(); resetForm(); renderTable(true); navigateTo('records'); renderChart();
        }
        function editStudent(i){ editIdx=i; const s=students[i]; document.getElementById('sName').value=s.name; document.getElementById('sRoll').value=s.roll; document.getElementById('sCourse').value=s.course; document.getElementById('sTotal').value=s.total; document.getElementById('sMarks').value=s.marks; document.getElementById('formTitle').innerText='Edit Student'; navigateTo('add'); }
        function deleteStudent(i){ if(!confirm('Delete this record?')) return; students.splice(i,1); persist(); renderTable(true); renderChart(); showToast('Deleted'); }
        function clearAll(){ if(confirm('Clear all records?')){ students=[]; persist(); renderTable(true); renderChart(); showToast('Cleared all'); } }
        function resetForm(){ document.getElementById('sName').value=''; document.getElementById('sRoll').value=''; document.getElementById('sCourse').value=''; document.getElementById('sTotal').value=100; document.getElementById('sMarks').value=0; editIdx=-1; document.getElementById('formTitle').innerText='Add Student'; }
        function persist(){ localStorage.setItem('students_v3', JSON.stringify(students)); document.getElementById('totalCount').innerText=students.length; }

        function getGrade(p){ if(p>=90) return 'A+'; if(p>=80) return 'A'; if(p>=70) return 'B+'; if(p>=60) return 'B'; if(p>=50) return 'C'; return 'F'; }

        // ----- Table render, real-time search with highlight, sort -----
        let currentSort='';
        function renderTable(highlight=false){
            const tbody=document.querySelector('#studentTable tbody'); tbody.innerHTML='';
            const q=document.getElementById('searchBox')?.value?.toLowerCase()||'';
            students.filter(s=> (s.name+s.roll+s.course+ (s.marks||'')).toString().toLowerCase().includes(q) ).forEach((s,i)=>{
                const tr=document.createElement('tr');
                const htmlName = highlight ? highlightMatch(s.name,q) : s.name;
                const htmlRoll = highlight ? highlightMatch(s.roll,q) : s.roll;
                const htmlCourse = highlight ? highlightMatch(s.course,q) : s.course;
                tr.innerHTML=`<td>${htmlName}</td><td>${htmlRoll}</td><td>${htmlCourse}</td><td>${s.marks}/${s.total} (${s.percent}%)</td><td>${s.grade}</td><td><button class='small' onclick='editStudent(${i})'>Edit</button> <button class='small' style='background:#a30a0a;color:#fff' onclick='deleteStudent(${i})'>Delete</button></td>`;
                tbody.appendChild(tr);
            });
            document.getElementById('totalCount').innerText=students.length;
        }
        function highlightMatch(text, q){ if(!q) return text; const idx = text.toLowerCase().indexOf(q); if(idx===-1) return text; return text.slice(0,idx)+'<span class="highlight">'+text.slice(idx, idx+q.length)+'</span>'+text.slice(idx+q.length); }
        function sortBy(field){ students.sort((a,b)=> (a[field]||'').toString().localeCompare((b[field]||'').toString())); persist(); renderTable(true); }

        // ----- Chart: course counts + marks distribution -----
        let courseChart=null; let marksChart=null;
        function renderChart(){
            const ctx=document.getElementById('courseChart').getContext('2d');
            const counts={}; const marks=[];
            students.forEach(s=>{ counts[s.course]=(counts[s.course]||0)+1; if(s.percent!==undefined) marks.push(s.percent); });
            const labels=Object.keys(counts); const data=Object.values(counts);
            if(courseChart) courseChart.destroy();
            courseChart=new Chart(ctx,{type:'bar', data:{labels, datasets:[{label:'Students per Course', data, backgroundColor:getGradient(ctx,data.length)}]}, options:{responsive:true, plugins:{legend:{display:false}}}});

            // stats
            const total=students.length; const avg = marks.length? Math.round(marks.reduce((a,b)=>a+b,0)/marks.length*100)/100 : 0; const top = marks.length? Math.max(...marks):0;
            document.getElementById('statTotal').innerText=total; document.getElementById('statAvg').innerText=avg+ '%'; document.getElementById('statTop').innerText=top+ '%';
        }
        function getGradient(ctx,n){ const base=['rgba(0,240,255,0.9)','rgba(122,0,255,0.9)','rgba(0,200,150,0.9)','rgba(255,180,0,0.9)']; return new Array(n).fill(0).map((_,i)=>base[i%base.length]); }

        // ----- Export PDF (html2canvas + jsPDF) -----
        async function exportPDF(){
            const wrap=document.getElementById('tableWrap');
            const canvas=await html2canvas(wrap,{scale:1.6});
            const img=canvas.toDataURL('image/png');
            const { jsPDF } = window.jspdf;
            const pdf=new jsPDF('p','mm','a4');
            const width=pdf.internal.pageSize.getWidth();
            const height= (canvas.height*width)/canvas.width;
            pdf.addImage(img,'PNG',8,8,width-16,height-16);
            pdf.save('students.pdf');
        }

        // ----- Export Excel (SheetJS) -----
        function exportExcel(){
            // include marks
            const ws=XLSX.utils.json_to_sheet(students);
            const wb=XLSX.utils.book_new(); XLSX.utils.book_append_sheet(wb,ws,'Students');
            XLSX.writeFile(wb,'students_with_marks.xlsx');
        }

        // ----- Theme toggles and animated dark mode + theme customizer -----
        function toggleTheme(){ document.body.classList.toggle('dark'); localStorage.setItem('theme', document.body.classList.contains('dark')?'dark':'light'); animateThemeSwitch(); }
        function toggleAnimatedTheme(){ document.body.classList.toggle('dark'); document.body.classList.add('animate-theme'); localStorage.setItem('theme', document.body.classList.contains('dark')?'dark':'light'); animateThemeSwitch(); }
        function animateThemeSwitch(){ const on=document.body.classList.contains('dark'); document.getElementById('themeSwitch').classList.toggle('on',on); document.getElementById('animatedThemeSwitch')?.classList.toggle('on',on); }
        function applyThemeColors(){ const a=document.getElementById('accentColor').value; const b=document.getElementById('accentColor2').value; document.documentElement.style.setProperty('--accent', a); document.documentElement.style.setProperty('--accent-2', b); showToast('Theme applied'); }

        // ----- Profile (avatar) -----
        function uploadAvatar(e){ const f=e.target.files[0]; if(!f) return; const r=new FileReader(); r.onload=()=>{ localStorage.setItem('srs_avatar', r.result); loadProfile(); showToast('Avatar saved'); }; r.readAsDataURL(f); }
        function loadProfile(){ const name=localStorage.getItem('srs_user')||''; const role=localStorage.getItem('srs_role')||'admin'; document.getElementById('profileName').value=name; document.getElementById('profileRole').value=role; const data=localStorage.getItem('srs_avatar'); const av=document.getElementById('avatarDisplay'); if(data){ av.style.backgroundImage=`url(${data})`; av.style.backgroundSize='cover'; av.innerText=''; } else { av.style.backgroundImage=''; av.innerText=name?name[0].toUpperCase():'A'; } }
        function saveProfile(){ const name=document.getElementById('profileName').value||'User'; const role=document.getElementById('profileRole').value; localStorage.setItem('srs_user', name); localStorage.setItem('srs_role', role); showToast('Profile saved'); }

        // ----- Toasts -----
        let toastTimer=null; function showToast(msg, err=false){ const t=document.getElementById('toast'); t.style.display='block'; t.style.background= err? 'linear-gradient(90deg,#ff4d4d,#e60000)' : 'linear-gradient(90deg,#00c6ff,#7a00ff)'; t.innerText=msg; clearTimeout(toastTimer); toastTimer=setTimeout(()=>{ t.style.display='none'; }, 3000); }

        // ----- Animated counters -----
        function animateStats(){ const total=document.getElementById('statTotal'); const avg=document.getElementById('statAvg'); const top=document.getElementById('statTop'); const tVal=students.length; const marksArr=students.map(s=>s.percent||0); const avgVal = marksArr.length? Math.round(marksArr.reduce((a,b)=>a+b,0)/marksArr.length*100)/100 : 0; const topVal = marksArr.length? Math.max(...marksArr):0; countUp(total, 0, tVal, 700); countUp(avg, 0, avgVal, 700, '%'); countUp(top, 0, topVal, 700, '%'); }
        function countUp(el, start, end, dur=800, suffix=''){ let startTs=null; const v=end; function step(ts){ if(!startTs) startTs=ts; const progress=(ts-startTs)/dur; const cur=Math.floor(progress*v + start); if(progress<1){ el.innerText= cur + suffix; requestAnimationFrame(step); } else { el.innerText = Math.round(v*100)/100 + suffix; } } requestAnimationFrame(step); }

        // ----- Init & helpers -----
        (function init(){
            // restore students and theme
            const lang = localStorage.getItem('lang')||'en'; document.getElementById('langSelect').value=lang; setLang(lang);
            document.getElementById('totalCount').innerText=students.length; renderTable(true); renderChart(); animateStats();
            const theme=localStorage.getItem('theme')||'light'; if(theme==='dark') document.body.classList.add('dark'); animateThemeSwitch();
            // demo avatar / profile
            loadProfile();
            // hide preloader after init
            setTimeout(()=>{ document.getElementById('preloader').style.display='none'; }, 700);
        })();

        // small helper for demo adding
        window.addDemoData = function(){ students.push({name:'Alice',roll:'101',course:'CS', total:100, marks:95, percent:95, grade:'A+'}); students.push({name:'Bob',roll:'102',course:'IT', total:100, marks:78, percent:78, grade:'B+'}); students.push({name:'Cara',roll:'103',course:'CS', total:100, marks:88, percent:88, grade:'A'}); persist(); renderTable(true); renderChart(); animateStats(); showToast('Demo data added'); }
    </script>
</body>
</html>
