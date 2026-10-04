</p>
from flask import Flask, render_template_string

app = Flask(__name__)

HTML_TEMPLATE = """
<!DOCTYPE html>
<html lang="en" class="dark">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Mohamed | Web Developer Portfolio</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <script>
        tailwind.config = {
            darkMode: 'class',
            theme: {
                extend: {
                    colors: {
                        primary: '#6366f1',
                        darkBg: '#0f172a',
                    }
                }
            }
        }
    </script>
</head>
<body class="bg-slate-950 text-slate-100 font-sans antialiased selection:bg-indigo-500 selection:text-white">

    <!-- Navbar -->
    <nav class="fixed top-0 left-0 right-0 z-50 bg-slate-900/80 backdrop-blur-md border-b border-slate-800">
        <div class="max-w-7xl mx-auto px-6 h-20 flex items-center justify-between">
            <a href="#" class="text-2xl font-black bg-gradient-to-r from-indigo-400 to-cyan-400 bg-clip-text text-transparent">Mohamed.dev</a>
            <div class="hidden md:flex items-center space-x-8 text-sm font-medium">
                <a href="#about" class="hover:text-indigo-400 transition">About</a>
                <a href="#skills" class="hover:text-indigo-400 transition">Skills</a>
                <a href="#contact" class="hover:text-indigo-400 transition">Contact</a>
            </div>
            <a href="tel:0771584397" class="bg-indigo-600 hover:bg-indigo-500 text-white px-5 py-2.5 rounded-full text-sm font-semibold transition shadow-lg shadow-indigo-600/30">
                <i class="fa-solid fa-phone mr-2"></i> 0771584397
            </a>
        </div>
    </nav>

    <!-- Hero Section -->
    <header class="min-h-screen flex items-center justify-center pt-20 relative overflow-hidden">
        <div class="absolute inset-0 bg-[radial-gradient(ellipse_at_top,_var(--tw-gradient-stops))] from-indigo-900/20 via-slate-950 to-slate-950 -z-10"></div>
        <div class="max-w-7xl mx-auto px-6 py-20 grid grid-cols-1 md:grid-cols-2 gap-12 items-center">
            <div class="space-y-6">
                <div class="inline-flex items-center space-x-2 bg-indigo-500/10 border border-indigo-500/20 px-3 py-1 rounded-full text-indigo-400 text-xs font-semibold uppercase tracking-wider">
                    <span class="w-2 h-2 rounded-full bg-indigo-500 animate-pulse"></span>
                    Available for Work
                </div>
                <h1 class="text-5xl md:text-7xl font-extrabold tracking-tight">
                    Hi, I'm <span class="bg-gradient-to-r from-indigo-400 via-purple-400 to-cyan-400 bg-clip-text text-transparent">Mohamed</span>
                </h1>
                <p class="text-xl text-slate-400 font-medium">Professional Web Developer building high-performance, modern web applications.</p>
                <div class="flex items-center space-x-4 pt-4">
                    <a href="#contact" class="bg-indigo-600 hover:bg-indigo-500 text-white font-semibold px-8 py-3.5 rounded-xl transition shadow-xl shadow-indigo-600/30">Get in Touch</a>
                    <a href="tel:0771584397" class="bg-slate-900 hover:bg-slate-800 text-slate-300 font-semibold px-8 py-3.5 rounded-xl border border-slate-800 transition">Call Now</a>
                </div>
            </div>
            <div class="flex justify-center">
                <div class="relative">
                    <div class="absolute -inset-1.5 bg-gradient-to-r from-indigo-500 to-cyan-500 rounded-3xl blur-xl opacity-30"></div>
                    <div class="relative w-72 h-72 md:w-80 md:h-80 bg-slate-900 border border-slate-800 rounded-3xl flex items-center justify-center overflow-hidden shadow-2xl">
                        <!-- مكان الصورة الـ Avatar -->
                        <div class="text-center p-6">
                            <i class="fa-solid fa-user-tie text-6xl text-indigo-500 mb-4"></i>
                            <p class="text-sm text-slate-300 font-bold">Mohamed</p>
                            <p class="text-xs text-indigo-400 mt-1">Web Developer</p>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </header>

    <!-- Skills Section -->
    <section id="skills" class="py-24 bg-slate-900/50 border-t border-slate-900">
        <div class="max-w-7xl mx-auto px-6">
            <h2 class="text-3xl font-bold text-center mb-16">My <span class="text-indigo-400">Tech Stack</span></h2>
            <div class="grid grid-cols-2 md:grid-cols-4 gap-6">
                <div class="bg-slate-900 border border-slate-800 p-6 rounded-2xl text-center hover:border-indigo-500/50 transition">
                    <i class="fa-brands fa-python text-4xl text-indigo-400 mb-3"></i>
                    <h3 class="font-bold text-lg">Python / Flask</h3>
                </div>
                <div class="bg-slate-900 border border-slate-800 p-6 rounded-2xl text-center hover:border-indigo-500/50 transition">
                    <i class="fa-brands fa-html5 text-4xl text-orange-500 mb-3"></i>
                    <h3 class="font-bold text-lg">HTML5 & CSS3</h3>
                </div>
                <div class="bg-slate-900 border border-slate-800 p-6 rounded-2xl text-center hover:border-indigo-500/50 transition">
                    <i class="fa-brands fa-js text-4xl text-yellow-400 mb-3"></i>
                    <h3 class="font-bold text-lg">JavaScript</h3>
                </div>
                <div class="bg-slate-900 border border-slate-800 p-6 rounded-2xl text-center hover:border-indigo-500/50 transition">
                    <i class="fa-brands fa-git-alt text-4xl text-red-500 mb-3"></i>
                    <h3 class="font-bold text-lg">Git & GitHub</h3>
                </div>
            </div>
        </div>
    </section>

    <!-- Contact Section -->
    <section id="contact" class="py-24">
        <div class="max-w-4xl mx-auto px-6 text-center">
            <h2 class="text-4xl font-extrabold mb-6">Let's Work <span class="text-indigo-400">Together</span></h2>
            <p class="text-slate-400 mb-10">Have a project in mind or want to hire me? Get in touch directly.</p>
            <div class="inline-flex flex-col md:flex-row items-center gap-6 bg-slate-900 border border-slate-800 p-8 rounded-3xl shadow-xl">
                <div class="flex items-center space-x-4">
                    <div class="w-12 h-12 rounded-full bg-indigo-500/10 flex items-center justify-center text-indigo-400">
                        <i class="fa-solid fa-phone text-lg"></i>
                    </div>
                    <div class="text-left">
                        <p class="text-xs text-slate-500 font-semibold uppercase">Phone / WhatsApp</p>
                        <a href="tel:0771584397" class="text-lg font-bold text-slate-200 hover:text-indigo-400 transition">0771584397</a>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Footer -->
    <footer class="py-8 border-t border-slate-900 text-center text-slate-500 text-sm">
        <p>&copy; 2026 Mohamed. All rights reserved.</p>
    </footer>

</body>
</html>
"""

@app.route('/')
def home():
    return render_template_string(HTML_TEMPLATE)

if __name__ == '__main__':
    print("🚀 Starting Flask server...")
    app.run(debug=True, port=5000)
