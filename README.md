import React, { useState, useEffect } from 'react';
import { BookOpen, Brain, Rocket, Users, Award, Code, Cloud, Zap, MessageSquare, Calendar, Github, Linkedin, Youtube, Mail, Star, TrendingUp, Cpu, Network } from 'lucide-react';

export default function Portfolio() {
  const [scrollY, setScrollY] = useState(0);
  const [activeSection, setActiveSection] = useState('home');

  useEffect(() => {
    const handleScroll = () => setScrollY(window.scrollY);
    window.addEventListener('scroll', handleScroll);
    return () => window.removeEventListener('scroll', handleScroll);
  }, []);

  const sections = [
    { id: 'home', label: 'Home' },
    { id: 'expertise', label: 'Expertise' },
    { id: 'services', label: 'Services' },
    { id: 'mentoring', label: 'Mentoring' },
    { id: 'tech', label: 'Tech Stack' },
    { id: 'contact', label: 'Contact' }
  ];

  const expertiseAreas = [
    {
      icon: <Brain className="w-12 h-12" />,
      title: "LLM & GenAI",
      description: "Building production-ready LLM applications, RAG systems, fine-tuning, prompt engineering, and GenAI solutions",
      skills: ["GPT-4", "Claude", "LangChain", "Vector DBs", "RAG Pipelines", "Prompt Engineering"]
    },
    {
      icon: <Network className="w-12 h-12" />,
      title: "AI Agents & MCP",
      description: "Developing autonomous AI agents, multi-agent systems, and Model Context Protocol integrations",
      skills: ["AutoGPT", "LangGraph", "Agent Orchestration", "MCP Integration", "Tool Calling", "Multi-Agent Systems"]
    },
    {
      icon: <Rocket className="w-12 h-12" />,
      title: "MLOps & AI-Ops",
      description: "End-to-end ML pipeline automation, model deployment, monitoring, and intelligent IT operations",
      skills: ["MLflow", "Kubeflow", "Model Serving", "A/B Testing", "Feature Stores", "AutoML"]
    },
    {
      icon: <Cloud className="w-12 h-12" />,
      title: "Cloud & Infrastructure",
      description: "Multi-cloud architecture, Kubernetes orchestration, and scalable AI infrastructure design",
      skills: ["AWS", "Azure", "GCP", "Kubernetes", "Terraform", "Docker"]
    }
  ];

  const services = [
    {
      icon: <Users className="w-10 h-10" />,
      title: "1:1 Mentoring",
      description: "Personalized career guidance and technical mentoring for AI/ML professionals",
      price: "Book on Topmate"
    },
    {
      icon: <BookOpen className="w-10 h-10" />,
      title: "Technical Training",
      description: "In-depth courses on LLM, GenAI, MLOps, and AI Agents implementation",
      price: "Custom Packages"
    },
    {
      icon: <Code className="w-10 h-10" />,
      title: "Consulting",
      description: "Enterprise AI strategy, architecture design, and implementation support",
      price: "Project-based"
    },
    {
      icon: <MessageSquare className="w-10 h-10" />,
      title: "Career Coaching",
      description: "Resume review, interview prep, and career transition guidance into AI/ML",
      price: "Book on Topmate"
    }
  ];

  const techStack = [
    { category: "LLM & GenAI", items: ["OpenAI", "Anthropic Claude", "LangChain", "LlamaIndex", "Hugging Face", "Pinecone"] },
    { category: "AI Agents & MCP", items: ["AutoGPT", "LangGraph", "CrewAI", "Model Context Protocol", "Function Calling", "Agent Tools"] },
    { category: "MLOps", items: ["MLflow", "Kubeflow", "Weights & Biases", "DVC", "BentoML", "Seldon Core"] },
    { category: "Cloud & DevOps", items: ["AWS", "Azure", "GCP", "Kubernetes", "Docker", "Terraform"] },
    { category: "ML/AI Frameworks", items: ["PyTorch", "TensorFlow", "Scikit-learn", "XGBoost", "FastAPI", "Streamlit"] },
    { category: "Monitoring", items: ["Prometheus", "Grafana", "Datadog", "ELK Stack", "New Relic", "Sentry"] }
  ];

  return (
    <div className="min-h-screen bg-gradient-to-br from-slate-900 via-purple-900 to-slate-900 text-white">
      {/* Navigation */}
      <nav className="fixed top-0 w-full bg-slate-900/80 backdrop-blur-md z-50 border-b border-purple-500/20">
        <div className="max-w-7xl mx-auto px-6 py-4">
          <div className="flex justify-between items-center">
            <div className="text-2xl font-bold bg-gradient-to-r from-cyan-400 to-purple-500 bg-clip-text text-transparent">
              Rajinikanth Vadla
            </div>
            <div className="hidden md:flex gap-6">
              {sections.map(section => (
                <a
                  key={section.id}
                  href={`#${section.id}`}
                  className="hover:text-cyan-400 transition-colors"
                  onClick={() => setActiveSection(section.id)}
                >
                  {section.label}
                </a>
              ))}
            </div>
          </div>
        </div>
      </nav>

      {/* Hero Section */}
      <section id="home" className="min-h-screen flex items-center justify-center relative overflow-hidden pt-20">
        <div className="absolute inset-0 overflow-hidden">
          <div className="absolute w-96 h-96 bg-purple-500/30 rounded-full blur-3xl -top-48 -left-48 animate-pulse"></div>
          <div className="absolute w-96 h-96 bg-cyan-500/30 rounded-full blur-3xl -bottom-48 -right-48 animate-pulse delay-700"></div>
        </div>
        
        <div className="max-w-7xl mx-auto px-6 text-center relative z-10">
          <div className="mb-8">
            <span className="inline-block px-4 py-2 bg-purple-500/20 border border-purple-500/50 rounded-full text-cyan-400 text-sm mb-6">
              🚀 AI-Ops Engineer | LLM & GenAI Specialist
            </span>
          </div>
          
          <h1 className="text-6xl md:text-8xl font-bold mb-6 bg-gradient-to-r from-cyan-400 via-purple-400 to-pink-400 bg-clip-text text-transparent animate-pulse">
            Rajinikanth Vadla
          </h1>
          
          <p className="text-2xl md:text-3xl mb-4 text-gray-300">
            Senior AI-Ops Engineer | MLOps Architect | GenAI Expert
          </p>
          
          <p className="text-xl text-gray-400 mb-8 max-w-3xl mx-auto">
            Specializing in <span className="text-cyan-400 font-semibold">LLM Applications</span>, 
            <span className="text-purple-400 font-semibold"> AI Agents</span>, 
            <span className="text-pink-400 font-semibold"> MLOps</span>, and 
            <span className="text-cyan-400 font-semibold"> Model Context Protocol (MCP)</span>
          </p>

          <div className="flex flex-wrap justify-center gap-4 mb-12">
            <a
              href="https://topmate.io/rajinikanthvadla/"
              target="_blank"
              rel="noopener noreferrer"
              className="px-8 py-4 bg-gradient-to-r from-cyan-500 to-purple-600 rounded-full font-semibold hover:shadow-2xl hover:shadow-cyan-500/50 transform hover:scale-105 transition-all duration-300 flex items-center gap-2"
            >
              <Calendar className="w-5 h-5" />
              Book Mentoring Session
            </a>
            <a
              href="#expertise"
              className="px-8 py-4 bg-slate-800/50 border border-purple-500/50 rounded-full font-semibold hover:bg-slate-700/50 transition-all duration-300"
            >
              Explore Expertise
            </a>
          </div>

          {/* Stats */}
          <div className="grid grid-cols-2 md:grid-cols-4 gap-6 max-w-4xl mx-auto">
            {[
              { label: "Years Experience", value: "5+" },
              { label: "LLM Projects", value: "50+" },
              { label: "Students Mentored", value: "200+" },
              { label: "Client Success", value: "99%" }
            ].map((stat, idx) => (
              <div key={idx} className="bg-slate-800/50 backdrop-blur-sm p-6 rounded-2xl border border-purple-500/20">
                <div className="text-3xl font-bold text-cyan-400 mb-2">{stat.value}</div>
                <div className="text-gray-400">{stat.label}</div>
              </div>
            ))}
          </div>
        </div>
      </section>

      {/* Expertise Section */}
      <section id="expertise" className="py-20 px-6">
        <div className="max-w-7xl mx-auto">
          <h2 className="text-5xl font-bold text-center mb-4 bg-gradient-to-r from-cyan-400 to-purple-500 bg-clip-text text-transparent">
            Core Expertise
          </h2>
          <p className="text-center text-gray-400 mb-16 text-xl">
            Building the future of AI with cutting-edge technologies
          </p>
          
          <div className="grid md:grid-cols-2 gap-8">
            {expertiseAreas.map((area, idx) => (
              <div
                key={idx}
                className="bg-slate-800/30 backdrop-blur-sm p-8 rounded-2xl border border-purple-500/20 hover:border-cyan-400/50 transition-all duration-300 hover:transform hover:scale-105 group"
              >
                <div className="text-cyan-400 mb-4 group-hover:scale-110 transition-transform">
                  {area.icon}
                </div>
                <h3 className="text-2xl font-bold mb-3 text-white">{area.title}</h3>
                <p className="text-gray-400 mb-4 leading-relaxed">{area.description}</p>
                <div className="flex flex-wrap gap-2">
                  {area.skills.map((skill, i) => (
                    <span
                      key={i}
                      className="px-3 py-1 bg-purple-500/20 border border-purple-500/30 rounded-full text-sm text-cyan-300"
                    >
                      {skill}
                    </span>
                  ))}
                </div>
              </div>
            ))}
          </div>
        </div>
      </section>

      {/* Services Section */}
      <section id="services" className="py-20 px-6 bg-slate-900/50">
        <div className="max-w-7xl mx-auto">
          <h2 className="text-5xl font-bold text-center mb-4 bg-gradient-to-r from-purple-400 to-pink-500 bg-clip-text text-transparent">
            Services Offered
          </h2>
          <p className="text-center text-gray-400 mb-16 text-xl">
            Empowering individuals and organizations with AI expertise
          </p>
          
          <div className="grid md:grid-cols-2 lg:grid-cols-4 gap-6">
            {services.map((service, idx) => (
              <div
                key={idx}
                className="bg-gradient-to-br from-slate-800/50 to-purple-900/30 p-6 rounded-2xl border border-purple-500/20 hover:border-cyan-400/50 transition-all duration-300 hover:transform hover:-translate-y-2"
              >
                <div className="text-purple-400 mb-4">{service.icon}</div>
                <h3 className="text-xl font-bold mb-2">{service.title}</h3>
                <p className="text-gray-400 mb-4 text-sm leading-relaxed">{service.description}</p>
                <div className="text-cyan-400 font-semibold">{service.price}</div>
              </div>
            ))}
          </div>
        </div>
      </section>

      {/* Mentoring CTA */}
      <section id="mentoring" className="py-20 px-6">
        <div className="max-w-5xl mx-auto">
          <div className="bg-gradient-to-r from-cyan-500/10 to-purple-500/10 backdrop-blur-sm p-12 rounded-3xl border border-purple-500/30 text-center">
            <Star className="w-16 h-16 text-cyan-400 mx-auto mb-6" />
            <h2 className="text-4xl font-bold mb-4">Ready to Level Up Your AI Career?</h2>
            <p className="text-xl text-gray-300 mb-8 max-w-2xl mx-auto">
              Get personalized mentoring in LLM development, GenAI applications, MLOps, AI Agents, and career guidance. 
              I've helped 200+ professionals transition into AI/ML roles.
            </p>
            
            <div className="grid md:grid-cols-3 gap-6 mb-8">
              {[
                { icon: <Brain />, title: "LLM & GenAI", desc: "Master production LLM apps" },
                { icon: <Network />, title: "AI Agents & MCP", desc: "Build autonomous systems" },
                { icon: <TrendingUp />, title: "Career Growth", desc: "Navigate your AI journey" }
              ].map((item, idx) => (
                <div key={idx} className="bg-slate-800/50 p-6 rounded-xl">
                  <div className="text-cyan-400 mb-3 flex justify-center">{item.icon}</div>
                  <h4 className="font-bold mb-2">{item.title}</h4>
                  <p className="text-sm text-gray-400">{item.desc}</p>
                </div>
              ))}
            </div>

            <a
              href="https://topmate.io/rajinikanthvadla/"
              target="_blank"
              rel="noopener noreferrer"
              className="inline-flex items-center gap-3 px-10 py-5 bg-gradient-to-r from-cyan-500 to-purple-600 rounded-full font-bold text-lg hover:shadow-2xl hover:shadow-purple-500/50 transform hover:scale-105 transition-all duration-300"
            >
              <Calendar className="w-6 h-6" />
              Book Your Session on Topmate
            </a>
          </div>
        </div>
      </section>

      {/* Tech Stack */}
      <section id="tech" className="py-20 px-6 bg-slate-900/50">
        <div className="max-w-7xl mx-auto">
          <h2 className="text-5xl font-bold text-center mb-4 bg-gradient-to-r from-cyan-400 to-purple-500 bg-clip-text text-transparent">
            Technology Stack
          </h2>
          <p className="text-center text-gray-400 mb-16 text-xl">
            Cutting-edge tools and frameworks for AI excellence
          </p>
          
          <div className="grid md:grid-cols-2 lg:grid-cols-3 gap-6">
            {techStack.map((category, idx) => (
              <div
                key={idx}
                className="bg-slate-800/30 backdrop-blur-sm p-6 rounded-2xl border border-purple-500/20"
              >
                <div className="flex items-center gap-2 mb-4">
                  <Cpu className="w-6 h-6 text-cyan-400" />
                  <h3 className="text-xl font-bold">{category.category}</h3>
                </div>
                <div className="flex flex-wrap gap-2">
                  {category.items.map((item, i) => (
                    <span
                      key={i}
                      className="px-3 py-1 bg-purple-500/20 border border-purple-500/30 rounded-lg text-sm hover:bg-purple-500/30 transition-colors"
                    >
                      {item}
                    </span>
                  ))}
                </div>
              </div>
            ))}
          </div>
        </div>
      </section>

      {/* Contact Section */}
      <section id="contact" className="py-20 px-6">
        <div className="max-w-4xl mx-auto text-center">
          <h2 className="text-5xl font-bold mb-8 bg-gradient-to-r from-cyan-400 to-purple-500 bg-clip-text text-transparent">
            Let's Connect
          </h2>
          
          <div className="flex flex-wrap justify-center gap-4 mb-12">
            <a
              href="https://topmate.io/rajinikanthvadla/"
              target="_blank"
              rel="noopener noreferrer"
              className="px-6 py-3 bg-gradient-to-r from-cyan-500 to-purple-600 rounded-full flex items-center gap-2 hover:shadow-lg hover:shadow-cyan-500/50 transition-all"
            >
              <Calendar className="w-5 h-5" />
              Topmate
            </a>
            <a
              href="https://linkedin.com/in/rajinikanthvadla"
              target="_blank"
              rel="noopener noreferrer"
              className="px-6 py-3 bg-slate-800 rounded-full flex items-center gap-2 hover:bg-slate-700 transition-all"
            >
              <Linkedin className="w-5 h-5" />
              LinkedIn
            </a>
            <a
              href="https://github.com/rajinikanthvadla-ai"
              target="_blank"
              rel="noopener noreferrer"
              className="px-6 py-3 bg-slate-800 rounded-full flex items-center gap-2 hover:bg-slate-700 transition-all"
            >
              <Github className="w-5 h-5" />
              GitHub
            </a>
            <a
              href="https://youtube.com/channel/ucefxgm7rc9wzmrf1uz7b4pa"
              target="_blank"
              rel="noopener noreferrer"
              className="px-6 py-3 bg-slate-800 rounded-full flex items-center gap-2 hover:bg-slate-700 transition-all"
            >
              <Youtube className="w-5 h-5" />
              YouTube
            </a>
            <a
              href="mailto:rajinikanth.vadla@gmail.com"
              className="px-6 py-3 bg-slate-800 rounded-full flex items-center gap-2 hover:bg-slate-700 transition-all"
            >
              <Mail className="w-5 h-5" />
              Email
            </a>
          </div>

          <div className="bg-slate-800/30 backdrop-blur-sm p-8 rounded-2xl border border-purple-500/20">
            <p className="text-gray-300 text-lg leading-relaxed">
              Whether you're looking to build production LLM applications, implement AI agents, 
              optimize your MLOps pipeline, integrate Model Context Protocol, or transition into AI/ML, 
              I'm here to help you succeed.
            </p>
            <p className="text-cyan-400 font-semibold mt-4 text-xl">
              Let's transform your AI journey together! 🚀
            </p>
          </div>
        </div>
      </section>

      {/* Footer */}
      <footer className="bg-slate-900/80 border-t border-purple-500/20 py-8 px-6">
        <div className="max-w-7xl mx-auto text-center">
          <p className="text-gray-400">
            © 2025 Rajinikanth Vadla - AI-Ops Engineer | LLM & GenAI Specialist | MLOps Architect
          </p>
          <p className="text-gray-500 mt-2 text-sm">
            Building the future of AI, one innovation at a time 🚀
          </p>
        </div>
      </footer>
    </div>
  );
}
