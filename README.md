import React from 'react';
import { Github, Linkedin, Mail, ExternalLink, Code2, Terminal, Cpu } from 'lucide-react';
import { motion } from 'framer-motion';

const App = () => {
  return (
    <div className="min-h-screen bg-[#030303] text-white selection:bg-purple-500/30">
      {/* Navigation */}
      <nav className="fixed top-0 w-full z-50 bg-black/50 backdrop-blur-md border-b border-white/10">
        <div className="max-w-6xl mx-auto px-6 h-16 flex items-center justify-between">
          <span className="text-xl font-bold tracking-tighter bg-gradient-to-r from-purple-400 to-pink-600 bg-clip-text text-transparent">
            ANUSH.SHW
          </span>
          <div className="hidden md:flex gap-8 text-sm font-medium text-gray-400">
            <a href="#about" className="hover:text-white transition-colors">About</a>
            <a href="#projects" className="hover:text-white transition-colors">Projects</a>
            <a href="#experience" className="hover:text-white transition-colors">Experience</a>
            <a href="#contact" className="hover:text-white transition-colors">Contact</a>
          </div>
        </div>
      </nav>

      {/* Hero Section */}
      <section className="pt-32 pb-20 px-6">
        <div className="max-w-4xl mx-auto text-center">
          <motion.div 
            initial={{ opacity: 0, y: 20 }}
            animate={{ opacity: 1, y: 0 }}
            transition={{ duration: 0.5 }}
          >
            <h1 className="text-5xl md:text-7xl font-bold mb-6 tracking-tight">
              Anush Shiwakoti
            </h1>
            <p className="text-xl md:text-2xl text-gray-400 mb-8 font-light">
              Full Stack Developer & UI/UX Designer
            </p>
            <div className="flex justify-center gap-4">
              <button className="bg-white text-black px-8 py-3 rounded-full font-semibold hover:bg-gray-200 transition-all">
                View Projects
              </button>
              <button className="border border-white/20 px-8 py-3 rounded-full font-semibold hover:bg-white/10 transition-all">
                Resume
              </button>
            </div>
          </motion.div>
        </div>
      </section>

      {/* Skills/Stacks */}
      <section className="py-20 bg-white/[0.02]">
        <div className="max-w-6xl mx-auto px-6">
          <div className="grid grid-cols-1 md:grid-cols-3 gap-8">
            <div className="p-8 rounded-2xl border border-white/10 bg-black/40">
              <Code2 className="text-purple-500 mb-4" size={32} />
              <h3 className="text-xl font-bold mb-2">Frontend</h3>
              <p className="text-gray-400">React, Next.js, Tailwind CSS, TypeScript.</p>
            </div>
            <div className="p-8 rounded-2xl border border-white/10 bg-black/40">
              <Terminal className="text-pink-500 mb-4" size={32} />
              <h3 className="text-xl font-bold mb-2">Backend</h3>
              <p className="text-gray-400">Node.js, PostgreSQL, Supabase, Python.</p>
            </div>
            <div className="p-8 rounded-2xl border border-white/10 bg-black/40">
              <Cpu className="text-blue-500 mb-4" size={32} />
              <h3 className="text-xl font-bold mb-2">Tools</h3>
              <p className="text-gray-400">Git, Docker, Figma, AWS.</p>
            </div>
          </div>
        </div>
      </section>

      {/* Projects Preview */}
      <section id="projects" className="py-20 px-6">
        <div className="max-w-6xl mx-auto">
          <h2 className="text-3xl font-bold mb-12">Featured Work</h2>
          <div className="grid grid-cols-1 md:grid-cols-2 gap-10">
            {[1, 2].map((i) => (
              <div key={i} className="group relative rounded-3xl overflow-hidden bg-gray-900 aspect-video border border-white/10">
                <div className="absolute inset-0 bg-gradient-to-t from-black to-transparent opacity-60" />
                <div className="absolute bottom-0 p-8">
                  <h3 className="text-2xl font-bold">Project Name {i}</h3>
                  <p className="text-gray-300 mt-2">Modern web application built with React.</p>
                  <ExternalLink className="mt-4 text-white/50 group-hover:text-white transition-colors" />
                </div>
              </div>
            ))}
          </div>
        </div>
      </section>

      {/* Footer */}
      <footer id="contact" className="py-20 border-t border-white/10">
        <div className="max-w-6xl mx-auto px-6 flex flex-col items-center">
          <h2 className="text-3xl font-bold mb-8">Get in Touch</h2>
          <div className="flex gap-6 mb-12">
            <a href="#" className="p-4 rounded-full bg-white/5 hover:bg-white/10 transition-colors">
              <Github size={24} />
            </a>
            <a href="#" className="p-4 rounded-full bg-white/5 hover:bg-white/10 transition-colors">
              <Linkedin size={24} />
            </a>
            <a href="#" className="p-4 rounded-full bg-white/5 hover:bg-white/10 transition-colors">
              <Mail size={24} />
            </a>
          </div>
          <p className="text-gray-500 text-sm">© 2024 Anush Shiwakoti. Built with Passion.</p>
        </div>
      </footer>
    </div>
  );
};

export default App;
