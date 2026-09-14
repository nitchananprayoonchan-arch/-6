<!DOCTYPE html>
<html lang="th">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>ระบบติดตามงานและคะแนนนักเรียน</title>
  
  <!-- Tailwind CSS CDN -->
  <script src="https://cdn.tailwindcss.com"></script>
  <!-- Google Fonts: Prompt & FontAwesome -->
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=Prompt:wght@300;400;500;600;700&display=swap" rel="stylesheet">
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">

  <style>
    body {
      font-family: 'Prompt', sans-serif;
      background: linear-gradient(135deg, #f0fdf4 0%, #e0f2fe 50%, #faf5ff 100%);
      min-height: 100vh;
    }
  </style>
</head>
<body class="text-slate-700 pb-16">

  <!-- แถบบอกสถานะ Online / Offline -->
  <div id="connection-status" class="py-1 px-4 text-xs font-medium text-center transition-colors duration-300 bg-emerald-500 text-white flex items-center justify-center gap-2">
    <span class="w-2 h-2 rounded-full bg-white animate-pulse"></span>
    <span id="status-text">ออนไลน์ (บันทึกข้อมูลในเครื่องพร้อมใช้งานตลอดเวลา)</span>
  </div>

  <!-- Navbar -->
  <nav class="bg-white/80 backdrop-blur-md border-b border-slate-200 px-4 py-3 sticky top-0 z-30 shadow-sm">
    <div class="max-w-4xl mx-auto flex items-center justify-between">
      <div class="flex items-center gap-2">
        <div class="w-9 h-9 rounded-xl bg-indigo-600 text-white flex items-center justify-center font-bold shadow-md shadow-indigo-200">
          <i class="fa-solid fa-graduation-cap"></i>
        </div>
        <span class="font-bold text-slate-800 text-sm sm:text-base hidden sm:inline">ระบบติดตามการเรียน</span>
      </div>

      <div class="flex items-center gap-3">
        <div id="user-badge" class="flex items-center gap-2 px-3 py-1.5 rounded-full text-xs font-semibold bg-indigo-50 text-indigo-700 border border-indigo-100"></div>
        <button onclick="openLoginModal()" class="px-3 py-1.5 text-xs font-medium text-slate-600 bg-slate-100 hover:bg-slate-200 rounded-xl transition-all flex items-center gap-1.5">
          <i class="fa-solid fa-arrow-right-from-bracket"></i>
          <span>สลับบทบาท / เข้าสู่ระบบ</span>
        </button>
      </div>
    </div>
  </nav>

  <div class="max-w-4xl mx-auto px-4 pt-6">

    <!-- แถบควบคุมสำหรับ "ครูผู้สอน" -->
    <div id="teacher-control-bar" class="hidden bg-gradient-to-r from-indigo-600 to-purple-600 rounded-3xl p-5 shadow-xl text-white mb-6">
      <div class="flex flex-col sm:flex-row items-start sm:items-center justify-between gap-4">
        <div>
          <span class="px-2.5 py-0.5 rounded-full bg-white/20 text-white text-[11px] font-semibold uppercase tracking-wider">โหมดครูผู้สอน</span>
          <h2 class="text-xl font-bold mt-1">แผงควบคุมและตรวจงานนักเรียน</h2>
          <p class="text-indigo-100 text-xs mt-0.5">เลือกนักเรียนเพื่อตรวจงาน หรือมอบหมายงานใหม่</p>
        </div>
        <div class="flex flex-wrap items-center gap-2 w-full sm:w-auto">
          <select id="teacher-student-selector" onchange="onSelectStudentFromTeacher(this.value)" class="flex-1 sm:flex-initial bg-white text-slate-800 font-medium px-4 py-2.5 rounded-xl text-sm focus:outline-none shadow-sm cursor-pointer">
            <!-- ตัวเลือกนักเรียน -->
          </select>
          <button onclick="openModal()" id="btn-add-task" class="px-4 py-2.5 bg-emerald-500 hover:bg-emerald-600 text-white font-medium rounded-xl text-sm shadow-md transition-all flex items-center justify-center gap-1.5">
            <i class="fa-solid fa-plus"></i> เพิ่มงานใหม่
          </button>
        </div>
      </div>
    </div>

    <!-- 1. การ์ดโปรไฟล์นักเรียน -->
    <div id="profile-card" class="bg-white/80 backdrop-blur-md rounded-3xl p-6 shadow-xl border border-white/40 mb-6 transition-all">
      <div class="flex flex-col sm:flex-row items-center gap-6">
        
        <!-- รูปโปรไฟล์ -->
        <div class="relative group cursor-pointer" onclick="triggerAvatarUpload()">
          <div class="w-24 h-24 sm:w-28 sm:h-28 rounded-full ring-4 ring-indigo-300 ring-offset-2 overflow-hidden shadow-inner bg-slate-100 flex items-center justify-center text-slate-400">
            <img id="profile-img" src="" alt="Avatar" class="w-full h-full object-cover hidden">
            <i id="profile-placeholder-icon" class="fa-solid fa-user text-4xl"></i>
          </div>
          <div class="absolute inset-0 bg-black/40 rounded-full flex items-center justify-center text-white opacity-0 group-hover:opacity-100 transition-opacity">
            <i class="fa-solid fa-camera text-xl"></i>
          </div>
          <input type="file" id="avatar-input" accept="image/*" class="hidden" onchange="changeAvatar(event)">
        </div>

        <!-- ชื่อและข้อมูลห้อง -->
        <div class="flex-1 text-center sm:text-left">
          <div class="flex items-center justify-center sm:justify-start gap-2">
            <h1 id="display-name" class="text-2xl sm:text-3xl font-bold text-slate-800">ยังไม่มีข้อมูลนักเรียน</h1>
            <button id="btn-edit-student-profile" onclick="openStudentRegistrationModal(true)" class="text-indigo-500 hover:text-indigo-600 p-1" title="แก้ไขข้อมูลของฉัน">
              <i class="fa-solid fa-pen-to-square"></i>
            </button>
          </div>
          <p id="display-class" class="text-slate-500 font-medium text-sm mt-1">กรุณากรอกข้อมูลนักเรียน</p>
          <div class="flex flex-wrap items-center justify-center sm:justify-start gap-2 mt-3">
            <span id="role-tag" class="px-3 py-1 bg-indigo-50 text-indigo-600 rounded-full text-xs font-semibold">
              สถานะ: นักเรียน
            </span>
            <span id="student-notice" class="hidden text-xs text-amber-600 bg-amber-50 px-2.5 py-1 rounded-full">
              <i class="fa-solid fa-lock text-[10px] mr-1"></i> นักเรียนดูได้เฉพาะงานและคะแนน
            </span>
          </div>
        </div>

      </div>
    </div>

    <!-- 2. Dashboard สรุปข้อมูลงานและคะแนน -->
    <div class="grid grid-cols-2 sm:grid-cols-4 gap-4 mb-6">
      <div class="bg-gradient-to-br from-blue-500 to-cyan-400 text-white p-4 rounded-2xl shadow-lg shadow-blue-100 flex flex-col items-center justify-center">
        <span class="text-xs font-medium opacity-90">งานทั้งหมด</span>
        <span id="stat-total" class="text-3xl font-extrabold mt-1">0</span>
        <span class="text-[10px] mt-1 opacity-75">ชิ้นงาน</span>
      </div>
      <div class="bg-gradient-to-br from-rose-500 to-orange-400 text-white p-4 rounded-2xl shadow-lg shadow-rose-100 flex flex-col items-center justify-center">
        <span class="text-xs font-medium opacity-90">งานค้าง</span>
        <span id="stat-pending" class="text-3xl font-extrabold mt-1">0</span>
        <span class="text-[10px] mt-1 opacity-75">ยังไม่เสร็จ</span>
      </div>
      <div class="bg-gradient-to-br from-emerald-500 to-teal-400 text-white p-4 rounded-2xl shadow-lg shadow-emerald-100 flex flex-col items-center justify-center">
        <span class="text-xs font-medium opacity-90">ส่งครบแล้ว</span>
        <span id="stat-completed" class="text-3xl font-extrabold mt-1">0</span>
        <span class="text-[10px] mt-1 opacity-75">เรียบร้อย</span>
      </div>
      <div class="bg-gradient-to-br from-amber-500 to-yellow-400 text-white p-4 rounded-2xl shadow-lg shadow-amber-100 flex flex-col items-center justify-center">
        <span class="text-xs font-medium opacity-90">คะแนนสะสม</span>
        <span id="stat-score" class="text-3xl font-extrabold mt-1">0/0</span>
        <span class="text-[10px] mt-1 opacity-75">คะแนนที่ได้/เต็ม</span>
      </div>
    </div>

    <!-- 3. แท็บกรองสถานะงาน -->
    <div class="flex items-center justify-between gap-2 mb-4">
      <div class="flex bg-slate-200/70 p-1 rounded-2xl text-xs sm:text-sm font-medium">
        <button onclick="filterTasks('all')" id="tab-all" class="px-3 sm:px-4 py-1.5 rounded-xl bg-white text-indigo-600 shadow-sm transition-all">ทั้งหมด</button>
        <button onclick="filterTasks('pending')" id="tab-pending" class="px-3 sm:px-4 py-1.5 rounded-xl text-slate-600 hover:text-slate-900 transition-all">ค้างอยู่</button>
        <button onclick="filterTasks('completed')" id="tab-completed" class="px-3 sm:px-4 py-1.5 rounded-xl text-slate-600 hover:text-slate-900 transition-all">เสร็จแล้ว</button>
      </div>
      <span id="task-count-label" class="text-xs text-slate-500">แสดงผล 0 รายการ</span>
    </div>

    <!-- 4. รายการการบ้าน/งาน -->
    <div id="tasks-container" class="space-y-3"></div>

    <!-- เมื่อไม่มีงาน -->
    <div id="empty-state" class="hidden flex-col items-center justify-center p-12 text-center bg-white/50 rounded-3xl border border-dashed border-slate-300">
      <div class="w-16 h-16 rounded-full bg-indigo-50 text-indigo-400 flex items-center justify-center text-2xl mb-3">
        <i class="fa-regular fa-folder-open"></i>
      </div>
      <p class="text-slate-600 font-semibold" id="empty-state-title">ไม่มีรายการงานในหมวดนี้</p>
      <p id="empty-state-sub" class="text-slate-400 text-sm mt-1"></p>
    </div>

  </div>

  <!-- Modal เลือกลงชื่อเข้าใช้ (Login / Switch Role Modal) -->
  <div id="login-modal" class="fixed inset-0 bg-slate-900/50 backdrop-blur-sm z-50 flex items-center justify-center p-4">
    <div class="bg-white rounded-3xl max-w-md w-full p-6 shadow-2xl">
      <div class="text-center mb-6">
        <div class="w-14 h-14 bg-indigo-50 text-indigo-600 rounded-2xl flex items-center justify-center text-2xl mx-auto mb-3 shadow-inner">
          <i class="fa-solid fa-user-lock"></i>
        </div>
        <h3 class="text-xl font-bold text-slate-800">เข้าสู่ระบบติดตามงาน</h3>
        <p class="text-xs text-slate-500 mt-1">กรุณาเลือกบทบาทในการเข้าใช้งานระบบ</p>
      </div>

      <!-- สลับแท็บ ครู / นักเรียน -->
      <div class="flex bg-slate-100 p-1 rounded-2xl mb-5">
        <button type="button" onclick="switchLoginTab('student')" id="btn-tab-student" class="flex-1 py-2 rounded-xl text-sm font-semibold transition-all bg-white text-indigo-600 shadow-sm">
          <i class="fa-solid fa-user-graduate mr-1"></i> นักเรียน
        </button>
        <button type="button" onclick="switchLoginTab('teacher')" id="btn-tab-teacher" class="flex-1 py-2 rounded-xl text-sm font-semibold transition-all text-slate-500 hover:text-slate-800">
          <i class="fa-solid fa-chalkboard-user mr-1"></i> ครูผู้สอน
        </button>
      </div>

      <!-- เข้าสู่ระบบของนักเรียน -->
      <div id="student-login-section" class="space-y-4">
        <div id="student-select-wrapper">
          <label class="block text-xs font-semibold text-slate-600 mb-1">เลือกโปรไฟล์ของฉัน:</label>
          <select id="login-student-select" class="w-full px-3 py-2.5 border border-slate-200 rounded-xl focus:outline-none focus:ring-2 focus:ring-indigo-400 text-sm font-medium bg-slate-50">
          </select>
        </div>

        <div class="flex flex-col gap-2">
          <button id="btn-login-student-action" onclick="loginAsExistingStudent()" class="w-full py-2.5 bg-indigo-600 hover:bg-indigo-700 text-white font-medium rounded-xl text-sm shadow-md transition-all">
            เข้าใช้งาน
          </button>
          <button onclick="openStudentRegistrationModal(false)" class="w-full py-2.5 bg-indigo-50 hover:bg-indigo-100 text-indigo-600 font-medium rounded-xl text-sm transition-all flex items-center justify-center gap-1.5">
            <i class="fa-solid fa-user-plus text-xs"></i> กรอกข้อมูลนักเรียนใหม่ (ลงทะเบียน)
          </button>
        </div>
        <p class="text-[11px] text-slate-400">หมายเหตุ: นักเรียนดูได้เฉพาะงานและคะแนนของตนเองเท่านั้น</p>
      </div>

      <!-- เข้าสู่ระบบของครู -->
      <div id="teacher-login-section" class="hidden space-y-4">
        <div class="p-3 bg-indigo-50/70 border border-indigo-100 rounded-2xl text-xs text-indigo-700 leading-relaxed">
          <i class="fa-solid fa-circle-info mr-1"></i> <strong>โหมดครูผู้สอน:</strong> สามารถดูรายชื่อนักเรียนทุกคน มอบหมายงาน ตรวจเช็คสถานะ และกรอกคะแนนได้
        </div>
        <button onclick="loginAsTeacher()" class="w-full py-3 bg-gradient-to-r from-indigo-600 to-purple-600 hover:opacity-95 text-white font-medium rounded-xl text-sm shadow-md transition-all">
          เข้าสู่ระบบในนามครูผู้สอน
        </button>
      </div>
    </div>
  </div>

  <!-- Modal สำหรับนักเรียนกรอกข้อมูลเอง (ลงทะเบียน / แก้ไขข้อมูลส่วนตัว) -->
  <div id="register-student-modal" class="fixed inset-0 bg-slate-900/60 backdrop-blur-sm z-50 flex items-center justify-center p-4 hidden">
    <div class="bg-white rounded-3xl max-w-md w-full p-6 shadow-2xl">
      <div class="flex items-center justify-between pb-3 border-b border-slate-100 mb-4">
        <h3 class="text-lg font-bold text-slate-800" id="register-modal-title">กรอกข้อมูลนักเรียน</h3>
        <button onclick="closeStudentRegistrationModal()" class="text-slate-400 hover:text-slate-600">
          <i class="fa-solid fa-xmark text-lg"></i>
        </button>
      </div>

      <form id="register-form" onsubmit="handleSaveStudentProfile(event)" class="space-y-4">
        <!-- รูปโปรไฟล์ขณะสมัคร -->
        <div class="flex flex-col items-center justify-center">
          <div class="relative group cursor-pointer" onclick="document.getElementById('reg-avatar-input').click()">
            <div class="w-20 h-20 rounded-full ring-2 ring-indigo-200 overflow-hidden bg-slate-100 flex items-center justify-center text-slate-400">
              <img id="reg-avatar-preview" src="" alt="" class="w-full h-full object-cover hidden">
              <i id="reg-avatar-icon" class="fa-solid fa-camera text-2xl"></i>
            </div>
            <input type="file" id="reg-avatar-input" accept="image/*" class="hidden" onchange="previewRegisterAvatar(event)">
          </div>
          <span class="text-[11px] text-slate-400 mt-1">คลิกรูปเพื่ออัปโหลดโปรไฟล์ (ไม่ใส่ก็ได้)</span>
        </div>

        <div>
          <label class="block text-xs font-semibold text-slate-600 mb-1">ชื่อ - นามสกุล *</label>
          <input type="text" id="reg-name" required placeholder="เช่น ด.ช. ณัฐวุฒิ สุขสบาย" class="w-full px-3 py-2 border border-slate-200 rounded-xl focus:outline-none focus:ring-2 focus:ring-indigo-400 text-sm">
        </div>

        <div class="grid grid-cols-2 gap-3">
          <div>
            <label class="block text-xs font-semibold text-slate-600 mb-1">ระดับชั้น / ห้อง *</label>
            <input type="text" id="reg-room" required placeholder="เช่น ม.2/1 หรือ ป.6" class="w-full px-3 py-2 border border-slate-200 rounded-xl focus:outline-none focus:ring-2 focus:ring-indigo-400 text-sm">
          </div>
          <div>
            <label class="block text-xs font-semibold text-slate-600 mb-1">เลขที่</label>
            <input type="text" id="reg-number" placeholder="เช่น 05 หรือ 12" class="w-full px-3 py-2 border border-slate-200 rounded-xl focus:outline-none focus:ring-2 focus:ring-indigo-400 text-sm">
          </div>
        </div>

        <div class="pt-2 flex gap-3">
          <button type="button" onclick="closeStudentRegistrationModal()" class="flex-1 py-2.5 bg-slate-100 text-slate-600 rounded-xl font-medium text-sm hover:bg-slate-200">ยกเลิก</button>
          <button type="submit" class="flex-1 py-2.5 bg-indigo-600 text-white rounded-xl font-medium text-sm hover:bg-indigo-700 shadow-md">บันทึกข้อมูล</button>
        </div>
      </form>
    </div>
  </div>

  <!-- Modal สำหรับ ครู มอบหมายงาน / ตรวจให้คะแนน -->
  <div id="task-modal" class="fixed inset-0 bg-slate-900/40 backdrop-blur-sm z-50 flex items-center justify-center p-4 hidden">
    <div class="bg-white rounded-3xl max-w-md w-full p-6 shadow-2xl">
      <div class="flex items-center justify-between pb-3 border-b border-slate-100">
        <h3 class="text-lg font-bold text-slate-800" id="modal-title">เพิ่มงานใหม่</h3>
        <button onclick="closeModal()" class="text-slate-400 hover:text-slate-600">
          <i class="fa-solid fa-xmark text-lg"></i>
        </button>
      </div>

      <form id="task-form" onsubmit="saveTask(event)" class="mt-4 space-y-4">
        <input type="hidden" id="task-id">

        <div>
          <label class="block text-xs font-semibold text-slate-600 mb-1">ชื่องาน / รายละเอียดงาน *</label>
          <input type="text" id="task-title" required placeholder="เช่น ใบงานวิชาคณิตศาสตร์เรื่องเศษส่วน" class="w-full px-3 py-2 border border-slate-200 rounded-xl focus:outline-none focus:ring-2 focus:ring-indigo-400 text-sm">
        </div>

        <div class="grid grid-cols-2 gap-3">
          <div>
            <label class="block text-xs font-semibold text-slate-600 mb-1">วิชา</label>
            <input type="text" id="task-subject" placeholder="เช่น วิทยาศาสตร์" class="w-full px-3 py-2 border border-slate-200 rounded-xl focus:outline-none focus:ring-2 focus:ring-indigo-400 text-sm">
          </div>
          <div>
            <label class="block text-xs font-semibold text-slate-600 mb-1">กำหนดส่ง</label>
            <input type="date" id="task-deadline" class="w-full px-3 py-2 border border-slate-200 rounded-xl focus:outline-none focus:ring-2 focus:ring-indigo-400 text-sm">
          </div>
        </div>

        <div class="grid grid-cols-2 gap-3">
          <div>
            <label class="block text-xs font-semibold text-slate-600 mb-1">คะแนนเต็ม</label>
            <input type="number" step="0.5" id="task-max-score" min="0" placeholder="เช่น 10" class="w-full px-3 py-2 border border-slate-200 rounded-xl focus:outline-none focus:ring-2 focus:ring-indigo-400 text-sm">
          </div>
          <div>
            <label class="block text-xs font-semibold text-slate-600 mb-1">คะแนนที่ได้ (ครูให้คะแนน)</label>
            <input type="number" step="0.5" id="task-score" min="0" placeholder="เช่น 9" class="w-full px-3 py-2 border border-slate-200 rounded-xl focus:outline-none focus:ring-2 focus:ring-indigo-400 text-sm">
          </div>
        </div>

        <div class="flex items-center gap-2 pt-1">
          <input type="checkbox" id="task-completed-checkbox" class="w-4 h-4 text-indigo-600 rounded border-slate-300 focus:ring-indigo-500">
          <label for="task-completed-checkbox" class="text-xs font-semibold text-slate-700 cursor-pointer">ตรวจแล้ว / ส่งครบแล้ว</label>
        </div>

        <div class="pt-2 flex gap-3">
          <button type="button" onclick="closeModal()" class="flex-1 py-2.5 bg-slate-100 text-slate-600 rounded-xl font-medium text-sm hover:bg-slate-200">ยกเลิก</button>
          <button type="submit" class="flex-1 py-2.5 bg-indigo-600 text-white rounded-xl font-medium text-sm hover:bg-indigo-700 shadow-md">บันทึก</button>
        </div>
      </form>
    </div>
  </div>

  <!-- JavaScript Logic -->
  <script>
    // เริ่มต้นด้วยอาร์เรย์ว่าง ไม่มีรายชื่อตายตัว
    let studentsData = JSON.parse(localStorage.getItem('app_students_custom')) || [];
    let currentUserRole = localStorage.getItem('app_user_role') || null; // 'teacher' | 'student'
    let currentStudentId = localStorage.getItem('app_current_student_id') || null;
    let currentFilter = 'all';
    let tempAvatarBase64 = null;
    let isEditingProfile = false;

    function saveAllData() {
      localStorage.setItem('app_students_custom', JSON.stringify(studentsData));
      localStorage.setItem('app_user_role', currentUserRole);
      localStorage.setItem('app_current_student_id', currentStudentId);
    }

    // ตรวจสอบสถานะออนไลน์/ออฟไลน์
    window.addEventListener('online', updateConnection);
    window.addEventListener('offline', updateConnection);

    function updateConnection() {
      const statusEl = document.getElementById('connection-status');
      const textEl = document.getElementById('status-text');
      if (navigator.onLine) {
        statusEl.className = "py-1 px-4 text-xs font-medium text-center transition-colors duration-300 bg-emerald-500 text-white flex items-center justify-center gap-2";
        textEl.textContent = "ออนไลน์ (บันทึกข้อมูลในเครื่องพร้อมใช้งานตลอดเวลา)";
      } else {
        statusEl.className = "py-1 px-4 text-xs font-medium text-center transition-colors duration-300 bg-amber-500 text-white flex items-center justify-center gap-2";
        textEl.textContent = "ออฟไลน์ (ใช้งานและบันทึกข้อมูลในเครื่องได้ปกติ)";
      }
    }

    // Modal สลับบทบาท / ล็อกอิน
    function openLoginModal() {
      populateStudentSelects();
      document.getElementById('login-modal').classList.remove('hidden');
    }

    function switchLoginTab(tab) {
      const btnStudent = document.getElementById('btn-tab-student');
      const btnTeacher = document.getElementById('btn-tab-teacher');
      const secStudent = document.getElementById('student-login-section');
      const secTeacher = document.getElementById('teacher-login-section');

      if (tab === 'student') {
        btnStudent.className = 'flex-1 py-2 rounded-xl text-sm font-semibold transition-all bg-white text-indigo-600 shadow-sm';
        btnTeacher.className = 'flex-1 py-2 rounded-xl text-sm font-semibold transition-all text-slate-500 hover:text-slate-800';
        secStudent.classList.remove('hidden');
        secTeacher.classList.add('hidden');
      } else {
        btnTeacher.className = 'flex-1 py-2 rounded-xl text-sm font-semibold transition-all bg-white text-indigo-600 shadow-sm';
        btnStudent.className = 'flex-1 py-2 rounded-xl text-sm font-semibold transition-all text-slate-500 hover:text-slate-800';
        secTeacher.classList.remove('hidden');
        secStudent.classList.add('hidden');
      }
    }

    function populateStudentSelects() {
      const loginSelect = document.getElementById('login-student-select');
      const teacherSelect = document.getElementById('teacher-student-selector');
      const selectWrapper = document.getElementById('student-select-wrapper');
      const btnLoginStudent = document.getElementById('btn-login-student-action');

      if (studentsData.length === 0) {
        selectWrapper.classList.add('hidden');
        btnLoginStudent.classList.add('hidden');
        if (teacherSelect) teacherSelect.innerHTML = '<option value="">ยังไม่มีข้อมูลนักเรียน</option>';
        return;
      }

      selectWrapper.classList.remove('hidden');
      btnLoginStudent.classList.remove('hidden');

      const options = studentsData.map(s => `<option value="${s.id}">${s.name} (${s.room} ${s.number ? 'เลขที่ ' + s.number : ''})</option>`).join('');
      
      if (loginSelect) loginSelect.innerHTML = options;
      if (teacherSelect) teacherSelect.innerHTML = options;
    }

    function loginAsExistingStudent() {
      const select = document.getElementById('login-student-select');
      if (!select.value) {
        openStudentRegistrationModal(false);
        return;
      }
      currentStudentId = select.value;
      currentUserRole = 'student';
      saveAllData();
      document.getElementById('login-modal').classList.add('hidden');
      initApp();
    }

    function loginAsTeacher() {
      currentUserRole = 'teacher';
      if (studentsData.length > 0 && !currentStudentId) {
        currentStudentId = studentsData[0].id;
      }
      saveAllData();
      document.getElementById('login-modal').classList.add('hidden');
      initApp();
    }

    function onSelectStudentFromTeacher(id) {
      currentStudentId = id;
      saveAllData();
      renderAppView();
    }

    // Modal กรอกข้อมูลนักเรียนเอง (ลงทะเบียน / แก้ไขข้อมูล)
    function openStudentRegistrationModal(edit = false) {
      isEditingProfile = edit;
      const modal = document.getElementById('register-student-modal');
      const title = document.getElementById('register-modal-title');
      const form = document.getElementById('register-form');
      form.reset();
      tempAvatarBase64 = null;

      const previewImg = document.getElementById('reg-avatar-preview');
      const previewIcon = document.getElementById('reg-avatar-icon');

      if (edit) {
        title.textContent = 'แก้ไขข้อมูลนักเรียน';
        const currentStudent = studentsData.find(s => s.id === currentStudentId);
        if (currentStudent) {
          document.getElementById('reg-name').value = currentStudent.name || '';
          document.getElementById('reg-room').value = currentStudent.room || '';
          document.getElementById('reg-number').value = currentStudent.number || '';
          if (currentStudent.avatar) {
            previewImg.src = currentStudent.avatar;
            previewImg.classList.remove('hidden');
            previewIcon.classList.add('hidden');
            tempAvatarBase64 = currentStudent.avatar;
          } else {
            previewImg.classList.add('hidden');
            previewIcon.classList.remove('hidden');
          }
        }
      } else {
        title.textContent = 'ลงทะเบียนข้อมูลนักเรียน';
        previewImg.classList.add('hidden');
        previewIcon.classList.remove('hidden');
      }

      document.getElementById('login-modal').classList.add('hidden');
      modal.classList.remove('hidden');
    }

    function closeStudentRegistrationModal() {
      document.getElementById('register-student-modal').classList.add('hidden');
      if (!currentUserRole) {
        openLoginModal();
      }
    }

    function previewRegisterAvatar(event) {
      const file = event.target.files[0];
      if (file) {
        const reader = new FileReader();
        reader.onload = function(e) {
          tempAvatarBase64 = e.target.result;
          const previewImg = document.getElementById('reg-avatar-preview');
          const previewIcon = document.getElementById('reg-avatar-icon');
          previewImg.src = tempAvatarBase64;
          previewImg.classList.remove('hidden');
          previewIcon.classList.add('hidden');
        };
        reader.readAsDataURL(file);
      }
    }

    function handleSaveStudentProfile(e) {
      e.preventDefault();
      const name = document.getElementById('reg-name').value.trim();
      const room = document.getElementById('reg-room').value.trim();
      const number = document.getElementById('reg-number').value.trim();

      if (!name || !room) return;

      if (isEditingProfile && currentStudentId) {
        // อัปเดตข้อมูลเดิม
        const student = studentsData.find(s => s.id === currentStudentId);
        if (student) {
          student.name = name;
          student.room = room;
          student.number = number;
          if (tempAvatarBase64) student.avatar = tempAvatarBase64;
        }
      } else {
        // เพิ่มนักเรียนใหม่
        const newStudent = {
          id: 'std_' + Date.now(),
          name: name,
          room: room,
          number: number,
          avatar: tempAvatarBase64 || '',
          tasks: []
        };
        studentsData.push(newStudent);
        currentStudentId = newStudent.id;
        currentUserRole = 'student';
      }

      saveAllData();
      document.getElementById('register-student-modal').classList.add('hidden');
      initApp();
    }

    // อัปโหลดเปลี่ยนรูปโปรไฟล์เมื่อคลิกที่อวตารโดยตรง
    function triggerAvatarUpload() {
      if (currentUserRole === 'student') {
        document.getElementById('avatar-input').click();
      }
    }

    function changeAvatar(event) {
      const file = event.target.files[0];
      if (file) {
        const reader = new FileReader();
        reader.onload = function(e) {
          const student = studentsData.find(s => s.id === currentStudentId);
          if (student) {
            student.avatar = e.target.result;
            saveAllData();
            renderAppView();
          }
        };
        reader.readAsDataURL(file);
      }
    }

    // เริ่มต้นระบบ
    function initApp() {
      if (!currentUserRole) {
        openLoginModal();
        return;
      }
      populateStudentSelects();
      renderAppView();
    }

    function renderAppView() {
      const isTeacher = currentUserRole === 'teacher';
      const teacherBar = document.getElementById('teacher-control-bar');
      const userBadge = document.getElementById('user-badge');
      const studentNotice = document.getElementById('student-notice');
      const btnEditProfile = document.getElementById('btn-edit-student-profile');

      if (isTeacher) {
        teacherBar.classList.remove('hidden');
        studentNotice.classList.add('hidden');
        btnEditProfile.classList.add('hidden');
        userBadge.className = 'flex items-center gap-2 px-3 py-1.5 rounded-full text-xs font-semibold bg-purple-100 text-purple-700 border border-purple-200';
        userBadge.innerHTML = '<i class="fa-solid fa-chalkboard-user"></i> เข้าใช้ในนาม: ครูผู้สอน';
        if (currentStudentId) {
          document.getElementById('teacher-student-selector').value = currentStudentId;
        }
      } else {
        teacherBar.classList.add('hidden');
        studentNotice.classList.remove('hidden');
        btnEditProfile.classList.remove('hidden');
        userBadge.className = 'flex items-center gap-2 px-3 py-1.5 rounded-full text-xs font-semibold bg-emerald-100 text-emerald-700 border border-emerald-200';
        userBadge.innerHTML = '<i class="fa-solid fa-user-graduate"></i> เข้าใช้ในนาม: นักเรียน';
      }

      // ตรวจสอบว่ามีนักเรียนที่เลือกอยู่หรือไม่
      const student = studentsData.find(s => s.id === currentStudentId);

      const profileImg = document.getElementById('profile-img');
      const profileIcon = document.getElementById('profile-placeholder-icon');

      if (!student) {
        // ยังไม่มีนักเรียนในระบบ
        document.getElementById('display-name').textContent = isTeacher ? 'ยังไม่มีนักเรียนลงทะเบียน' : 'ยังไม่ได้กรอกข้อมูล';
        document.getElementById('display-class').textContent = isTeacher ? 'กรุณารอนักเรียนลงทะเบียนเข้าใช้' : 'คลิกเพื่อกรอกข้อมูลของตัวเอง';
        document.getElementById('role-tag').textContent = isTeacher ? 'โหมดครูผู้สอน' : 'โหมดนักเรียน';
        profileImg.classList.add('hidden');
        profileIcon.classList.remove('hidden');

        updateDashboard({ tasks: [] });
        renderTasks({ tasks: [] }, true);
        return;
      }

      document.getElementById('display-name').textContent = student.name;
      document.getElementById('display-class').textContent = `ห้อง ${student.room} ${student.number ? '• เลขที่ ' + student.number : ''}`;
      document.getElementById('role-tag').textContent = isTeacher ? `กำลังตรวจงานของ: ${student.name}` : 'สมุดติดตามงานของฉัน';

      if (student.avatar) {
        profileImg.src = student.avatar;
        profileImg.classList.remove('hidden');
        profileIcon.classList.add('hidden');
      } else {
        profileImg.classList.add('hidden');
        profileIcon.classList.remove('hidden');
      }

      updateDashboard(student);
      renderTasks(student, false);
    }

    function updateDashboard(student) {
      const tasks = student.tasks || [];
      const total = tasks.length;
      const completed = tasks.filter(t => t.completed).length;
      const pending = total - completed;

      let currentScore = 0;
      let totalMaxScore = 0;

      tasks.forEach(t => {
        if (t.score !== null && t.score !== undefined && t.score !== '') {
          currentScore += parseFloat(t.score);
        }
        if (t.maxScore) {
          totalMaxScore += parseFloat(t.maxScore);
        }
      });

      document.getElementById('stat-total').textContent = total;
      document.getElementById('stat-pending').textContent = pending;
      document.getElementById('stat-completed').textContent = completed;
      document.getElementById('stat-score').textContent = `${currentScore}/${totalMaxScore}`;
    }

    function renderTasks(student, noStudent = false) {
      const container = document.getElementById('tasks-container');
      const emptyState = document.getElementById('empty-state');
      const emptyTitle = document.getElementById('empty-state-title');
      const emptySub = document.getElementById('empty-state-sub');
      const isTeacher = currentUserRole === 'teacher';

      if (noStudent) {
        container.innerHTML = '';
        emptyState.classList.remove('hidden');
        emptyState.classList.add('flex');
        emptyTitle.textContent = isTeacher ? 'ยังไม่มีนักเรียนในระบบ' : 'ยังไม่ได้ลงทะเบียน';
        emptySub.textContent = isTeacher ? 'ให้นักเรียนเข้าเว็บและกด "กรอกข้อมูลนักเรียนใหม่"' : 'กรุณากดสลับผู้ใช้เพื่อลงทะเบียนชื่อตนเอง';
        return;
      }

      let filtered = student.tasks || [];
      if (currentFilter === 'pending') {
        filtered = filtered.filter(t => !t.completed);
      } else if (currentFilter === 'completed') {
        filtered = filtered.filter(t => t.completed);
      }

      document.getElementById('task-count-label').textContent = `แสดงผล ${filtered.length} รายการ`;

      if (filtered.length === 0) {
        container.innerHTML = '';
        emptyState.classList.remove('hidden');
        emptyState.classList.add('flex');
        emptyTitle.textContent = 'ไม่มีรายการงานในหมวดนี้';
        emptySub.textContent = isTeacher ? 'กดปุ่ม "+ เพิ่มงานใหม่" เพื่อสั่งงานให้นักเรียนคนนี้' : 'ยังไม่มีงานที่คุณครูมอบหมายในหมวดนี้';
        return;
      }

      emptyState.classList.add('hidden');
      emptyState.classList.remove('flex');

      container.innerHTML = filtered.map(task => {
        const isDone = task.completed;
        return `
          <div class="bg-white/90 backdrop-blur-sm border ${isDone ? 'border-emerald-100 bg-emerald-50/20' : 'border-slate-200'} rounded-2xl p-4 shadow-sm hover:shadow-md transition-all flex flex-col sm:flex-row items-start sm:items-center justify-between gap-4">
            
            <div class="flex items-start gap-3 flex-1">
              <button ${isTeacher ? `onclick="toggleComplete('${task.id}')"` : 'disabled'} 
                class="mt-1 flex-shrink-0 w-6 h-6 rounded-lg border-2 ${isDone ? 'bg-emerald-500 border-emerald-500 text-white' : 'border-slate-300'} ${isTeacher ? 'cursor-pointer hover:border-indigo-400' : 'cursor-default'} flex items-center justify-center transition-colors">
                ${isDone ? '<i class="fa-solid fa-check text-xs"></i>' : ''}
              </button>
              <div>
                <h4 class="font-semibold text-slate-800 ${isDone ? 'line-through text-slate-400' : ''}">
                  ${escapeHtml(task.title)}
                </h4>
                <div class="flex flex-wrap gap-2 items-center mt-1 text-xs">
                  ${task.subject ? `<span class="px-2 py-0.5 rounded-md bg-indigo-50 text-indigo-600 font-medium">${escapeHtml(task.subject)}</span>` : ''}
                  ${task.deadline ? `<span class="text-slate-400"><i class="fa-regular fa-clock mr-1"></i>ส่ง: ${task.deadline}</span>` : ''}
                  <span class="px-2 py-0.5 rounded-md text-[11px] font-semibold ${isDone ? 'bg-emerald-100 text-emerald-700' : 'bg-rose-100 text-rose-700'}">
                    ${isDone ? 'ส่งแล้ว' : 'ยังไม่ส่ง'}
                  </span>
                </div>
              </div>
            </div>

            <div class="flex items-center justify-between w-full sm:w-auto gap-4 border-t sm:border-t-0 pt-2 sm:pt-0 border-slate-100">
              <div class="text-right">
                ${task.maxScore ? `
                  <div class="text-xs font-semibold ${task.score !== null && task.score !== '' ? 'text-indigo-600' : 'text-slate-400'}">
                    คะแนน: <span class="text-base font-bold">${task.score !== null && task.score !== '' ? task.score : '-'}</span>/${task.maxScore}
                  </div>
                ` : '<span class="text-xs text-slate-300">ไม่มีคะแนน</span>'}
              </div>

              ${isTeacher ? `
                <div class="flex items-center gap-1">
                  <button onclick="openModal('${task.id}')" class="p-2 text-slate-400 hover:text-indigo-500 rounded-lg transition-colors" title="ตรวจคะแนน / แก้ไข">
                    <i class="fa-solid fa-pen text-sm"></i>
                  </button>
                  <button onclick="deleteTask('${task.id}')" class="p-2 text-slate-400 hover:text-rose-500 rounded-lg transition-colors" title="ลบงาน">
                    <i class="fa-solid fa-trash-can text-sm"></i>
                  </button>
                </div>
              ` : ''}
            </div>

          </div>
        `;
      }).join('');
    }

    function filterTasks(filter) {
      currentFilter = filter;
      const tabs = ['all', 'pending', 'completed'];
      tabs.forEach(tab => {
        const btn = document.getElementById(`tab-${tab}`);
        if (tab === filter) {
          btn.className = 'px-3 sm:px-4 py-1.5 rounded-xl bg-white text-indigo-600 shadow-sm transition-all font-medium';
        } else {
          btn.className = 'px-3 sm:px-4 py-1.5 rounded-xl text-slate-600 hover:text-slate-900 transition-all';
        }
      });
      const student = studentsData.find(s => s.id === currentStudentId);
      renderTasks(student || { tasks: [] }, !student);
    }

    // การจัดการงานของครู
    function toggleComplete(taskId) {
      if (currentUserRole !== 'teacher') return;
      const student = studentsData.find(s => s.id === currentStudentId);
      if (!student) return;
      const task = student.tasks.find(t => t.id === taskId);
      if (task) {
        task.completed = !task.completed;
        saveAllData();
        renderAppView();
      }
    }

    function deleteTask(taskId) {
      if (currentUserRole !== 'teacher') return;
      if (confirm('คุณครูต้องการลบงานนี้ของนักเรียนใช่หรือไม่?')) {
        const student = studentsData.find(s => s.id === currentStudentId);
        if (student) {
          student.tasks = student.tasks.filter(t => t.id !== taskId);
          saveAllData();
          renderAppView();
        }
      }
    }

    function openModal(taskId = null) {
      if (currentUserRole !== 'teacher') return;
      if (!currentStudentId) {
        alert('กรุณาเลือกหรือรอนักเรียนลงทะเบียนก่อนมอบหมายงาน');
        return;
      }

      const modal = document.getElementById('task-modal');
      const form = document.getElementById('task-form');
      form.reset();

      if (taskId) {
        const student = studentsData.find(s => s.id === currentStudentId);
        const task = student?.tasks.find(t => t.id === taskId);
        if (task) {
          document.getElementById('modal-title').textContent = 'แก้ไขงาน / ตรวจให้คะแนน';
          document.getElementById('task-id').value = task.id;
          document.getElementById('task-title').value = task.title;
          document.getElementById('task-subject').value = task.subject || '';
          document.getElementById('task-deadline').value = task.deadline || '';
          document.getElementById('task-max-score').value = task.maxScore || '';
          document.getElementById('task-score').value = task.score !== null ? task.score : '';
          document.getElementById('task-completed-checkbox').checked = !!task.completed;
        }
      } else {
        document.getElementById('modal-title').textContent = 'มอบหมายงานใหม่ให้นักเรียน';
        document.getElementById('task-id').value = '';
        document.getElementById('task-completed-checkbox').checked = false;
      }

      modal.classList.remove('hidden');
    }

    function closeModal() {
      document.getElementById('task-modal').classList.add('hidden');
    }

    function saveTask(e) {
      e.preventDefault();
      if (currentUserRole !== 'teacher') return;

      const student = studentsData.find(s => s.id === currentStudentId);
      if (!student) return;

      const id = document.getElementById('task-id').value;
      const title = document.getElementById('task-title').value.trim();
      const subject = document.getElementById('task-subject').value.trim();
      const deadline = document.getElementById('task-deadline').value;
      const maxScore = document.getElementById('task-max-score').value;
      const score = document.getElementById('task-score').value;
      const completed = document.getElementById('task-completed-checkbox').checked;

      if (!title) return;

      if (id) {
        const task = student.tasks.find(t => t.id === id);
        if (task) {
          task.title = title;
          task.subject = subject;
          task.deadline = deadline;
          task.maxScore = maxScore ? parseFloat(maxScore) : null;
          task.score = score !== '' ? parseFloat(score) : null;
          task.completed = completed;
        }
      } else {
        if (!student.tasks) student.tasks = [];
        student.tasks.unshift({
          id: Date.now().toString(),
          title: title,
          subject: subject,
          deadline: deadline,
          maxScore: maxScore ? parseFloat(maxScore) : null,
          score: score !== '' ? parseFloat(score) : null,
          completed: completed
        });
      }

      saveAllData();
      renderAppView();
      closeModal();
    }

    function escapeHtml(text) {
      if (!text) return '';
      return text.replace(/&/g, "&amp;").replace(/</g, "&lt;").replace(/>/g, "&gt;").replace(/"/g, "&quot;").replace(/'/g, "&#039;");
    }

    // เริ่มทำงานครั้งแรก
    updateConnection();
    initApp();
  </script>
</body>
</html>
