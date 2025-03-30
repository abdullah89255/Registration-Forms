# Registration-Forms
I assume you meant "create a registration form (graphics design) for a WordPress website (students form and teachers form)." I’ll create two stylish registration forms—one for students and one for teachers—with a "graphics design" aesthetic (vibrant colors, modern layout, creative typography) that you can integrate into a WordPress site. Each form will collect relevant data tailored to its audience (e.g., student ID for students, subject for teachers). I’ll provide:

1. **HTML/CSS Code**: Two forms with distinct designs.
2. **WordPress Integration**: Steps to add them using a plugin or custom code.
3. **Security Note**: Basic tips to secure the forms against vulnerabilities like XSS.

---

### Step 1: HTML/CSS for Graphics Design Registration Forms

#### Students Registration Form
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Student Registration</title>
    <style>
        body {
            font-family: 'Poppins', sans-serif;
            background: linear-gradient(135deg, #6b48ff, #00ddeb);
            display: flex;
            justify-content: center;
            align-items: center;
            min-height: 100vh;
            margin: 0;
        }
        .form-container {
            background: rgba(255, 255, 255, 0.95);
            padding: 40px;
            border-radius: 20px;
            box-shadow: 0 10px 20px rgba(0, 0, 0, 0.2);
            width: 100%;
            max-width: 450px;
        }
        h2 {
            text-align: center;
            color: #6b48ff;
            font-size: 32px;
            margin-bottom: 25px;
            text-transform: uppercase;
            letter-spacing: 3px;
        }
        .form-group {
            margin-bottom: 20px;
        }
        label {
            color: #333;
            font-weight: 600;
            margin-bottom: 8px;
            display: block;
        }
        input[type="text"],
        input[type="email"],
        input[type="password"],
        input[type="number"] {
            width: 100%;
            padding: 12px;
            border: none;
            border-radius: 10px;
            background: #f5f5f5;
            font-size: 16px;
            color: #333;
            transition: all 0.3s ease;
        }
        input:focus {
            outline: none;
            background: #fff;
            box-shadow: 0 0 8px rgba(107, 72, 255, 0.5);
        }
        button {
            width: 100%;
            padding: 14px;
            background: linear-gradient(90deg, #6b48ff, #00ddeb);
            border: none;
            border-radius: 10px;
            color: white;
            font-size: 18px;
            font-weight: bold;
            cursor: pointer;
            transition: transform 0.2s;
        }
        button:hover {
            transform: scale(1.03);
        }
    </style>
</head>
<body>
    <div class="form-container">
        <h2>Student Sign-Up</h2>
        <form action="/wp-login.php?action=register" method="post">
            <div class="form-group">
                <label for="student_name">Full Name</label>
                <input type="text" id="student_name" name="student_name" required>
            </div>
            <div class="form-group">
                <label for="student_email">Email</label>
                <input type="email" id="student_email" name="user_email" required>
            </div>
            <div class="form-group">
                <label for="student_id">Student ID</label>
                <input type="text" id="student_id" name="student_id" required>
            </div>
            <div class="form-group">
                <label for="student_pass">Password</label>
                <input type="password" id="student_pass" name="user_pass" required>
            </div>
            <button type="submit">Join Now</button>
        </form>
    </div>
</body>
</html>
```

**Design Features**:
- Gradient background (purple to cyan) for a youthful, creative vibe.
- Clean, rounded inputs with a focus glow effect.
- Bold, uppercase heading for emphasis.

#### Teachers Registration Form
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Teacher Registration</title>
    <style>
        body {
            font-family: 'Montserrat', sans-serif;
            background: linear-gradient(135deg, #ff9f1c, #2ab7ca);
            display: flex;
            justify-content: center;
            align-items: center;
            min-height: 100vh;
            margin: 0;
        }
        .form-container {
            background: rgba(255, 255, 255, 0.9);
            padding: 40px;
            border-radius: 15px;
            box-shadow: 0 12px 24px rgba(0, 0, 0, 0.25);
            width: 100%;
            max-width: 450px;
        }
        h2 {
            text-align: center;
            color: #ff9f1c;
            font-size: 30px;
            margin-bottom: 25px;
            text-transform: uppercase;
            letter-spacing: 2puncheds: 2px;
        }
        .form-group {
            margin-bottom: 20px;
        }
        label {
            color: #333;
            font-weight: bold;
            margin-bottom: 8px;
            display: block;
        }
        input[type="text"],
        input[type="email"],
        input[type="password"] {
            width: 100%;
            padding: 12px;
            border: 2px solid #ff9f1c;
            border-radius: 8px;
            background: #fef5e7;
            font-size: 16px;
            color: #333;
            transition: all 0.3s ease;
        }
        input:focus {
            outline: none;
            border-color: #2ab7ca;
            background: #fff;
        }
        button {
            width: 100%;
            padding: 14px;
            background: linear-gradient(90deg, #ff9f1c, #2ab7ca);
            border: none;
            border-radius: 8px;
            color: white;
            font-size: 18px;
            font-weight: bold;
            cursor: pointer;
            transition: transform 0.2s;
        }
        button:hover {
            transform: scale(1.03);
        }
    </style>
</head>
<body>
    <div class="form-container">
        <h2>Teacher Sign-Up</h2>
        <form action="/wp-login.php?action=register" method="post">
            <div class="form-group">
                <label for="teacher_name">Full Name</label>
                <input type="text" id="teacher_name" name="teacher_name" required>
            </div>
            <div class="form-group">
                <label for="teacher_email">Email</label>
                <input type="email" id="teacher_email" name="user_email" required>
            </div>
            <div class="form-group">
                <label for="subject">Subject Taught</label>
                <input type="text" id="subject" name="subject" required>
            </div>
            <div class="form-group">
                <label for="teacher_pass">Password</label>
                <input type="password" id="teacher_pass" name="user_pass" required>
            </div>
            <button type="submit">Register Now</button>
        </form>
    </div>
</body>
</html>
```

**Design Features**:
- Warm gradient (orange to teal) for a professional yet approachable feel.
- Bordered inputs with a subtle background for contrast.
- Clean, structured layout for clarity.

---

### Step 2: WordPress Integration

#### Option 1: Using WPForms Plugin
1. **Install WPForms**:
   - Dashboard > Plugins > Add New > Search "WPForms" > Install & Activate.
2. **Create Forms**:
   - **Student Form**: WPForms > Add New > "User Registration Form" > Add fields (Name, Email, Student ID, Password) > Save.
   - **Teacher Form**: Repeat, replacing Student ID with Subject Taught.
   - Get shortcodes (e.g., `[wpforms id="123"]` for students, `[wpforms id="124"]` for teachers).
3. **Style**:
   - Appearance > Customize > Additional CSS > Paste CSS, adjusting selectors:
     ```css
     /* Student Form */
     .wpforms-form#wpforms-form-123 {
         background: rgba(255, 255, 255, 0.95);
         padding: 40px;
         border-radius: 20px;
         box-shadow: 0 10px 20px rgba(0, 0, 0, 0.2);
     }
     /* Add rest of student CSS with .wpforms-form#wpforms-form-123 prefix */

     /* Teacher Form */
     .wpforms-form#wpforms-form-124 {
         background: rgba(255, 255, 255, 0.9);
         padding: 40px;
         border-radius: 15px;
         box-shadow: 0 12px 24px rgba(0, 0, 0, 0.25);
     }
     /* Add rest of teacher CSS with .wpforms-form#wpforms-form-124 prefix */
     ```
4. **Embed**:
   - Create two pages (e.g., "Student Registration" and "Teacher Registration").
   - Add respective shortcodes and publish.

#### Option 2: Custom Code
1. **Create Page Templates**:
   - In `wp-content/themes/your-theme/`:
     - `page-student-register.php`:
       ```php
       <?php
       /*
        * Template Name: Student Registration
        */
       get_header();
       ?>
       <!-- Paste Student HTML here -->
       <?php
       get_footer();
       ```
     - `page-teacher-register.php`:
       ```php
       <?php
       /*
        * Template Name: Teacher Registration
        */
       get_header();
       ?>
       <!-- Paste Teacher HTML here -->
       <?php
       get_footer();
       ```
2. **Handle Registration in `functions.php`**:
   ```php
   function custom_register_users() {
       if ($_SERVER['REQUEST_METHOD'] === 'POST') {
           $nonce = wp_create_nonce('custom_register');
           if (!isset($_POST['nonce']) || !wp_verify_nonce($_POST['nonce'], 'custom_register')) {
               die('Security check failed');
           }

           $email = sanitize_email($_POST['user_email']);
           $password = $_POST['user_pass'];

           if (isset($_POST['student_name'])) {
               $username = sanitize_user($_POST['student_name']);
               $meta = ['student_id' => sanitize_text_field($_POST['student_id'])];
               $role = 'subscriber'; // Student role
           } elseif (isset($_POST['teacher_name'])) {
               $username = sanitize_user($_POST['teacher_name']);
               $meta = ['subject' => sanitize_text_field($_POST['subject'])];
               $role = 'contributor'; // Teacher role
           } else {
               return;
           }

           $user_id = wp_create_user($username, $password, $email);
           if (!is_wp_error($user_id)) {
               foreach ($meta as $key => $value) {
                   update_user_meta($user_id, $key, $value);
               }
               wp_set_auth_cookie($user_id);
               wp_set_current_user($user_id);
               wp_redirect(home_url());
               exit;
           } else {
               echo "<p>Error: " . $user_id->get_error_message() . "</p>";
           }
       }
   }
   add_action('init', 'custom_register_users');

   // Add nonce to forms
   function add_nonce_to_forms() {
       if (is_page_template('page-student-register.php') || is_page_template('page-teacher-register.php')) {
           echo '<input type="hidden" name="nonce" value="' . wp_create_nonce('custom_register') . '">';
       }
   }
   add_action('wp_footer', 'add_nonce_to_forms');
   ```
   - Update form actions in HTML to `<?php echo esc_url(home_url('/')); ?>`.
3. **Add Pages**:
   - Pages > Add New > "Student Registration" (use Student Registration template).
   - Pages > Add New > "Teacher Registration" (use Teacher Registration template).

---
