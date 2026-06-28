# Answers

---

## About You

### 1. Introduce yourself.

Hi, I'm Dominic K Joseph from Thrissur, Kerala. I completed my B.Tech in Computer Science from Thejus Engineering College.

I have around two years of experience in web development. Most recently, I worked as a Software Engineer at Axel Technologies. Before that, I worked as a PHP Developer at Esight Business Solutions, and I started my career with a six-month internship as a PHP Full Stack Developer at Nosce Techno Solutions.

My primary expertise is in Laravel and React, and I've worked on developing full-stack web applications, including database design, REST APIs, and responsive user interfaces. I enjoy writing clean, maintainable code, learning new technologies, and taking on challenging projects that help me grow as a developer.


### 2. Describe your development environment.

- **OS:** Windows 11
- **Editor:** Visual Studio Code
- **Terminal:** Git Bash / Windows Terminal
- **Local Server:** Laravel's built-in dev server (`php artisan serve`)
- **Version Control:** Git with GitHub
- **Database GUI:** phpMyAdmin
- **Config Manager:** `.env` files managed per project

### 3. Which programming languages are installed on your system?

- PHP 8.2
- JavaScript / Node.js
- Python (occasional scripting)
- SQL (MySQL)
- Golang

### 4. Any programming language interested to learn next?

Go (Golang). The performance and concurrency model genuinely interest me. I plan to build something small with it soon to get a proper feel for it.
---

## Social Profile

### 1. GitHub profile URL
https://github.com/Dominic-K-Joseph

### 2. LinkedIn profile
www.linkedin.com/in/dominic-k-joseph-8670b6286

### 3. Personal website / blog
**CareerCraft** is my personal job portal project built with **Laravel, Blade, JavaScript, and MySQL**. It's currently running in my local development environment and is not publicly hosted yet. The application features **Admin, Employer, and Job Seeker dashboards**, role-based access, job posting and application management, RESTful APIs, real-time messaging with Socket.IO, an instruction-based chatbot, bulk email functionality, scheduled tasks using Laravel Scheduler etc. I plan to deploy it once the remaining features are completed and fully tested. 
---

## The Real Stuff

### 1. Function that takes a number and returns an array of its digits

```php
function getDigits($number)
{
    return array_map('intval', str_split((string) abs($number)));
}

// Usage
print_r(getDigits(12345)); //[1,2,3,4,5]
```

---

### 2. Pig Latin translator (English to Pig Latin and back)

```php
function toPigLatin($text)
{
    $words = explode(' ', $text);

    foreach ($words as &$word) {
        $word = substr($word, 1) . $word[0] . 'ay';
    }

    return implode(' ', $words);
}

// Usage
echo toPigLatin("Join with yellowfish"); // "oinjay ithway ellowfishyay"

function fromPigLatin($text)
{
    $words = explode(' ', $text);

    foreach ($words as &$word) {

        // Remove "ay"
        $word = substr($word, 0, -2);

        // Last character becomes first
        $word = substr($word, -1) . substr($word, 0, -1);
    }

    return implode(' ', $words);
}

// Usage
echo fromPigLatin("oinJay ithway ellowfishyay"); // "Join with yellowfish"
```

---

### 3. Rotate array by k elements (in-place, no copy)

```php
function rotateArray(array &$arr, int $k): void
{
    $k = $k % count($arr);
    
    for ($i = 0; $i < $k; $i++) {
        $first = array_shift($arr);
        array_push($arr, $first);
    }
}

// Usage
$arr = [1, 2, 3, 4, 5, 6];
rotateArray($arr, 2);
print_r($arr); // [3, 4, 5, 6, 1, 2]
```
---

### 4. ERP System — Option 2: URL Shortener

**Repository:** https://github.com/Dominic-K-Joseph/url-shortener

Features implemented:
- Laravel Auth (Sign Up / Sign In / Logout)
- Dashboard with total URL count snapshot card
- URL list with add form (Ajax, no page reload, newest first)
- Custom short URL generation (no external API)
- URL validation (client + server side)
- Copy-to-clipboard button per row
- AdminLTE 3 template
- Eloquent ORM + Laravel Migrations