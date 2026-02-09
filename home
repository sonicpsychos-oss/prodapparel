import React, { useState, useEffect } from 'react';
import { 
  Camera, 
  Clapperboard, 
  Gift, 
  Clock, 
  CheckCircle, 
  Menu, 
  X, 
  ArrowRight, 
  Scissors, 
  Layers,
  Phone,
  Zap,
  ChevronRight,
  FileText,
  ScanLine,
  Maximize2,
  Download
} from 'lucide-react';

const App = () => {
  // --- STATE MANAGEMENT ---
  const [isScrolled, setIsScrolled] = useState(false);
  const [isMobileMenuOpen, setIsMobileMenuOpen] = useState(false);
  const [isQuoteOpen, setIsQuoteOpen] = useState(false);
  
  // Quote Wizard State
  const [wizardStep, setWizardStep] = useState(1);
  const [formData, setFormData] = useState({
    type: '',
    quantity: '',
    deadline: '',
    email: ''
  });
  const [formSuccess, setFormSuccess] = useState(false);

  // --- EFFECTS ---
  useEffect(() => {
    const handleScroll = () => {
      setIsScrolled(window.scrollY > 50);
    };
    window.addEventListener('scroll', handleScroll);
    return () => window.removeEventListener('scroll', handleScroll);
  }, []);

  // --- HANDLERS ---
  const handleNextStep = () => setWizardStep((prev) => prev + 1);
  const handlePrevStep = () => setWizardStep((prev) => prev - 1);
  const updateData = (field, value) => setFormData({ ...formData, [field]: value });
  
  const submitForm = () => {
    setTimeout(() => {
      setFormSuccess(true);
      setTimeout(() => {
        setIsQuoteOpen(false);
        setFormSuccess(false);
        setWizardStep(1);
        setFormData({ type: '', quantity: '', deadline: '', email: '' });
      }, 4000);
    }, 1500);
  };

  return (
    <div className="min-h-screen bg-zinc-950 text-zinc-100 font-sans selection:bg-lime-400 selection:text-zinc-900 pb-24 md:pb-0">
      
      {/* --- NAVIGATION --- */}
      <nav className={`fixed top-0 left-0 right-0 z-50 transition-all duration-300 border-b ${isScrolled ? 'bg-zinc-950/90 backdrop-blur-md border-zinc-800 py-3' : 'bg-transparent border-transparent py-6'}`}>
        <div className="max-w-7xl mx-auto px-6 flex justify-between items-center">
          <div className="flex items-center gap-2">
            <div className="w-8 h-8 bg-lime-400 text-zinc-950 flex items-center justify-center font-bold tracking-tighter text-xl rounded-sm">
              P/A
            </div>
            <span className="font-bold tracking-tight text-xl hidden sm:block">PROD/APPAREL</span>
          </div>

          <div className="hidden md:flex items-center gap-8 text-sm font-medium text-zinc-400">
            <a href="#services" className="hover:text-lime-400 transition-colors">DEPARTMENTS</a>
            <a href="#work" className="hover:text-lime-400 transition-colors">THE VAULT</a>
            <a href="#process" className="hover:text-lime-400 transition-colors">WORKFLOW</a>
          </div>

          <div className="flex items-center gap-4">
             <button onClick={() => setIsQuoteOpen(true)} className="hidden md:flex items-center gap-2 bg-zinc-100 text-zinc-900 px-5 py-2.5 text-sm font-bold hover:bg-lime-400 transition-colors duration-300 rounded-sm">
              START ORDER <ArrowRight size={16} />
            </button>
            <button onClick={() => setIsMobileMenuOpen(!isMobileMenuOpen)} className="md:hidden text-zinc-100">
              {isMobileMenuOpen ? <X /> : <Menu />}
            </button>
          </div>
        </div>
      </nav>

      {/* --- MOBILE MENU --- */}
      {isMobileMenuOpen && (
        <div className="fixed inset-0 z-40 bg-zinc-950 pt-24 px-6 md:hidden border-l border-zinc-800">
          <div className="flex flex-col gap-8 text-2xl font-bold uppercase tracking-tight">
            <a href="#services" onClick={() => setIsMobileMenuOpen(false)}>Departments</a>
            <a href="#work" onClick={() => setIsMobileMenuOpen(false)}>Past Work</a>
            <a href="#process" onClick={() => setIsMobileMenuOpen(false)}>Workflow</a>
            <button onClick={() => {setIsMobileMenuOpen(false); setIsQuoteOpen(true)}} className="text-lime-400 text-left">Get A Quote</button>
          </div>
        </div>
      )}

      {/* --- MOBILE STICKY CTA --- */}
      <div className="md:hidden fixed bottom-0 left-0 right-0 z-40 bg-zinc-900 border-t border-zinc-800 p-4 pb-8 backdrop-blur-lg">
        <button onClick={() => setIsQuoteOpen(true)} className="w-full bg-lime-400 text-zinc-950 font-bold py-4 rounded-sm shadow-lg shadow-lime-400/20 flex items-center justify-center gap-2 uppercase tracking-wide">
          Start Order Now <ArrowRight size={18} />
        </button>
      </div>

      {/* --- HERO SECTION --- */}
      <header className="relative pt-32 pb-20 lg:pt-48 lg:pb-32 overflow-hidden">
        {/* Abstract Background Elements */}
        <div className="absolute top-0 right-0 w-1/2 h-full bg-gradient-to-l from-zinc-900 to-transparent opacity-50 -z-10"></div>
        <div className="absolute bottom-0 left-0 w-full h-px bg-gradient-to-r from-transparent via-lime-400/50 to-transparent"></div>

        <div className="max-w-7xl mx-auto px-6 grid lg:grid-cols-2 gap-12 items-center">
          <div className="space-y-8">
            <div className="inline-flex items-center gap-2 px-3 py-1 border border-zinc-800 rounded-sm bg-zinc-900/50 text-xs font-mono text-lime-400 tracking-wider">
              <Zap size={12} className="fill-lime-400 animate-pulse" />
              RUSH ORDERS: OPEN
            </div>
            
            <h1 className="text-5xl lg:text-7xl font-bold tracking-tighter leading-[0.9]">
              WE DRESS THE <br />
              <span className="text-transparent bg-clip-text bg-gradient-to-r from-zinc-100 to-zinc-500">
                PRODUCTION.
              </span>
            </h1>
            
            <p className="text-lg text-zinc-400 max-w-md leading-relaxed">
              From crew hoodies to on-screen props. We are the industry's dedicated apparel partner. Fast, discreet, and production-grade.
            </p>

            <div className="flex flex-col sm:flex-row gap-4">
              <button onClick={() => setIsQuoteOpen(true)} className="bg-lime-400 text-zinc-950 px-8 py-4 font-bold text-lg hover:bg-lime-300 transition-colors flex items-center justify-center gap-2 rounded-sm">
                GET A QUOTE
              </button>
              <button className="border border-zinc-700 text-zinc-300 px-8 py-4 font-bold text-lg hover:border-zinc-500 hover:text-white transition-colors flex items-center justify-center gap-2 rounded-sm">
                THE LEDGER
              </button>
            </div>
            
            <div className="pt-8 border-t border-zinc-800 flex items-center gap-8 text-zinc-500 font-mono text-xs">
              <div>
                <span className="block text-xl font-bold text-zinc-100">10k+</span>
                UNITS SHIPPED
              </div>
              <div>
                <span className="block text-xl font-bold text-zinc-100">600+</span>
                ORDERS FULFILLED
              </div>
              <div>
                <span className="block text-xl font-bold text-zinc-100">100%</span>
                IN-HOUSE
              </div>
            </div>
          </div>

          <div className="relative h-[400px] lg:h-[600px] bg-zinc-900 rounded-sm overflow-hidden border border-zinc-800 group">
             {/* Visual Placeholder for 'Production Set' */}
             <div className="absolute inset-0 bg-[radial-gradient(circle_at_center,_var(--tw-gradient-stops))] from-zinc-800 to-zinc-950 flex items-center justify-center">
                <div className="text-center space-y-4 opacity-50 group-hover:opacity-100 transition-opacity duration-500">
                    <Camera size={64} className="mx-auto text-zinc-700" />
                    <p className="font-mono text-sm tracking-widest text-zinc-500">IMG_SET_001.RAW</p>
                </div>
             </div>
             
             {/* Floating Badge */}
             <div className="absolute bottom-6 right-6 bg-zinc-950/90 backdrop-blur border-l-2 border-lime-400 p-4 max-w-[200px]">
                <p className="text-xs text-zinc-500 font-mono mb-1">TURNAROUND EST.</p>
                <div className="flex items-center gap-2 text-zinc-100 font-bold">
                    <Clock size={16} className="text-lime-400" />
                    <span>48 HOURS (RUSH)</span>
                </div>
             </div>
          </div>
        </div>
      </header>

      {/* --- TRUST TICKER --- */}
      <div className="w-full bg-zinc-900/30 border-y border-zinc-800 py-6 overflow-hidden">
        <div className="max-w-7xl mx-auto px-6 flex flex-col md:flex-row items-center gap-6 md:gap-12">
            <span className="text-xs font-bold text-zinc-500 font-mono uppercase tracking-widest whitespace-nowrap">Production Partners:</span>
            <div className="flex gap-12 opacity-40 grayscale hover:grayscale-0 transition-all duration-500 items-center overflow-x-auto w-full no-scrollbar">
                {["NETFLIX", "A24", "HBO", "WARNER BROS", "UNIVERSAL", "INDIE WIRE"].map((brand, i) => (
                    <span key={i} className="font-black text-xl text-zinc-300 tracking-tighter whitespace-nowrap">{brand}</span>
                ))}
            </div>
        </div>
      </div>

      {/* --- SERVICES --- */}
      <section id="services" className="py-24 bg-zinc-900/20">
        <div className="max-w-7xl mx-auto px-6">
          <div className="mb-16 md:flex justify-between items-end">
            <div>
              <h2 className="text-3xl md:text-5xl font-bold mb-4 tracking-tight">DEPARTMENT NEEDS</h2>
              <p className="text-zinc-400">Select your category. We handle the rest.</p>
            </div>
            <div className="hidden md:block text-right font-mono text-xs text-zinc-500">
              SERVICE_MENU_V2.0
            </div>
          </div>

          <div className="grid md:grid-cols-3 gap-6">
            {/* Card 1: Crew */}
            <div className="group relative bg-zinc-950 border border-zinc-800 hover:border-lime-400/50 transition-all duration-300 h-[400px] flex flex-col justify-between p-6 overflow-hidden rounded-sm">
              <div className="absolute top-0 right-0 p-4 opacity-20 group-hover:opacity-100 transition-opacity">
                <Clapperboard size={40} />
              </div>
              <div className="z-10 mt-auto">
                <span className="inline-block px-2 py-1 mb-3 text-[10px] font-mono border border-zinc-700 text-lime-400 bg-zinc-900 uppercase">Volume Pricing</span>
                <h3 className="text-2xl font-bold mb-2 group-hover:text-lime-400 transition-colors">THE CREW</h3>
                <p className="text-zinc-400 text-sm mb-6 leading-relaxed">
                  High-durability hoodies, vests, and tees. Identification for Camera, Grip, and Electric departments.
                </p>
                <button onClick={() => setIsQuoteOpen(true)} className="flex items-center gap-2 text-sm font-bold uppercase tracking-wider border-b border-zinc-700 pb-1 group-hover:border-lime-400 transition-colors">
                  Outfit The Team <ArrowRight size={14} />
                </button>
              </div>
              <div className="absolute inset-0 bg-gradient-to-t from-zinc-950 via-zinc-950/20 to-transparent pointer-events-none"></div>
            </div>

            {/* Card 2: Wardrobe/Props */}
            <div className="group relative bg-zinc-950 border border-zinc-800 hover:border-lime-400/50 transition-all duration-300 h-[400px] flex flex-col justify-between p-6 overflow-hidden rounded-sm">
              <div className="absolute top-0 right-0 p-4 opacity-20 group-hover:opacity-100 transition-opacity">
                <Scissors size={40} />
              </div>
              <div className="z-10 mt-auto">
                <span className="inline-block px-2 py-1 mb-3 text-[10px] font-mono border border-zinc-700 text-lime-400 bg-zinc-900 uppercase">Fast Fabrication</span>
                <h3 className="text-2xl font-bold mb-2 group-hover:text-lime-400 transition-colors">WARDROBE & PROPS</h3>
                <p className="text-zinc-400 text-sm mb-6 leading-relaxed">
                  Fictional branding, specific uniforms, and period-accurate prints. Screen-ready assets for Art Dept.
                </p>
                <button onClick={() => setIsQuoteOpen(true)} className="flex items-center gap-2 text-sm font-bold uppercase tracking-wider border-b border-zinc-700 pb-1 group-hover:border-lime-400 transition-colors">
                  Start Fabrication <ArrowRight size={14} />
                </button>
              </div>
              <div className="absolute inset-0 bg-gradient-to-t from-zinc-950 via-zinc-950/20 to-transparent pointer-events-none"></div>
            </div>

            {/* Card 3: Wrap Gifts */}
            <div className="group relative bg-zinc-950 border border-zinc-800 hover:border-lime-400/50 transition-all duration-300 h-[400px] flex flex-col justify-between p-6 overflow-hidden rounded-sm">
              <div className="absolute top-0 right-0 p-4 opacity-20 group-hover:opacity-100 transition-opacity">
                <Gift size={40} />
              </div>
              <div className="z-10 mt-auto">
                <span className="inline-block px-2 py-1 mb-3 text-[10px] font-mono border border-zinc-700 text-lime-400 bg-zinc-900 uppercase">Premium Quality</span>
                <h3 className="text-2xl font-bold mb-2 group-hover:text-lime-400 transition-colors">THE WRAP</h3>
                <p className="text-zinc-400 text-sm mb-6 leading-relaxed">
                  Premium embroidered jackets, bags, and laser-engraved goods. End the production on a high note.
                </p>
                <button onClick={() => setIsQuoteOpen(true)} className="flex items-center gap-2 text-sm font-bold uppercase tracking-wider border-b border-zinc-700 pb-1 group-hover:border-lime-400 transition-colors">
                  Browse Premium <ArrowRight size={14} />
                </button>
              </div>
              <div className="absolute inset-0 bg-gradient-to-t from-zinc-950 via-zinc-950/20 to-transparent pointer-events-none"></div>
            </div>
          </div>
        </div>
      </section>

      {/* --- WE SPEAK PRODUCTION (THE LEDGER) --- */}
      <section id="work" className="py-24 max-w-7xl mx-auto px-6 border-t border-zinc-800">
        <div className="grid lg:grid-cols-2 gap-16 items-start">
          <div className="sticky top-32">
            <h2 className="text-4xl md:text-5xl font-bold mb-8 leading-[0.9] tracking-tighter">
              WE SPEAK <br/>
              <span className="text-zinc-500">PRODUCTION.</span>
            </h2>
            
            <div className="space-y-8 mb-12">
              <div className="flex items-start gap-5">
                <div className="w-12 h-12 bg-zinc-900 border border-zinc-800 flex items-center justify-center shrink-0 rounded-sm">
                  <Clock className="text-lime-400" />
                </div>
                <div>
                  <h4 className="font-bold text-xl mb-1">Deadlines are Sacred</h4>
                  <p className="text-zinc-400 text-sm leading-relaxed max-w-sm">
                    We know if it's not there by call time, it's useless. We maintain a 99.9% on-time delivery rate for set-critical assets.
                  </p>
                </div>
              </div>

              <div className="flex items-start gap-5">
                <div className="w-12 h-12 bg-zinc-900 border border-zinc-800 flex items-center justify-center shrink-0 rounded-sm">
                  <Layers className="text-lime-400" />
                </div>
                <div>
                  <h4 className="font-bold text-xl mb-1">Asset Archiving</h4>
                  <p className="text-zinc-400 text-sm leading-relaxed max-w-sm">
                    Need to match a shirt from a shoot 6 months ago for reshoots? We keep your production files on standby for 2 years.
                  </p>
                </div>
              </div>
            </div>

            <button onClick={() => setIsQuoteOpen(true)} className="border border-zinc-700 hover:border-lime-400 hover:text-lime-400 text-zinc-300 px-8 py-4 font-bold tracking-wider uppercase transition-colors rounded-sm">
              View Full Lookbook
            </button>
          </div>

          <div className="grid grid-cols-2 gap-4">
            {/* Image 1: Textural/Macro shot */}
            <div className="group relative aspect-square bg-zinc-900 rounded-sm overflow-hidden border border-zinc-800 cursor-pointer">
               <img src="/api/placeholder/400/400" alt="Embroidered Hoodie Detail" className="w-full h-full object-cover opacity-60 group-hover:opacity-100 group-hover:scale-110 transition-all duration-500 grayscale group-hover:grayscale-0" />
               <div className="absolute inset-0 bg-gradient-to-t from-zinc-950 via-transparent to-transparent opacity-80"></div>
               <div className="absolute bottom-4 left-4">
                 <p className="text-[10px] font-mono text-lime-400 mb-1">CREW_GEAR</p>
                 <p className="font-bold text-sm">Heavyweight Embroidery</p>
               </div>
               <div className="absolute top-4 right-4 bg-zinc-950/50 p-2 rounded-full opacity-0 group-hover:opacity-100 transition-opacity">
                 <Maximize2 size={16} />
               </div>
            </div>

            {/* Image 2: On-Screen Prop */}
            <div className="group relative aspect-square bg-zinc-900 rounded-sm overflow-hidden border border-zinc-800 cursor-pointer mt-8">
               <img src="/api/placeholder/400/400" alt="Fictional Uniform" className="w-full h-full object-cover opacity-60 group-hover:opacity-100 group-hover:scale-110 transition-all duration-500 grayscale group-hover:grayscale-0" />
               <div className="absolute inset-0 bg-gradient-to-t from-zinc-950 via-transparent to-transparent opacity-80"></div>
               <div className="absolute bottom-4 left-4">
                 <p className="text-[10px] font-mono text-lime-400 mb-1">ART_DEPT</p>
                 <p className="font-bold text-sm">Fictional Uniforms</p>
               </div>
            </div>

            {/* Image 3: Action Shot */}
            <div className="group relative aspect-square bg-zinc-900 rounded-sm overflow-hidden border border-zinc-800 cursor-pointer">
               <img src="/api/placeholder/400/400" alt="Crew on Set" className="w-full h-full object-cover opacity-60 group-hover:opacity-100 group-hover:scale-110 transition-all duration-500 grayscale group-hover:grayscale-0" />
               <div className="absolute inset-0 bg-gradient-to-t from-zinc-950 via-transparent to-transparent opacity-80"></div>
               <div className="absolute bottom-4 left-4">
                 <p className="text-[10px] font-mono text-lime-400 mb-1">ON_LOCATION</p>
                 <p className="font-bold text-sm">Camera Dept. Vests</p>
               </div>
            </div>

            {/* Image 4: Premium Gift */}
            <div className="group relative aspect-square bg-zinc-900 rounded-sm overflow-hidden border border-zinc-800 cursor-pointer mt-8">
               <img src="/api/placeholder/400/400" alt="Leather Bag" className="w-full h-full object-cover opacity-60 group-hover:opacity-100 group-hover:scale-110 transition-all duration-500 grayscale group-hover:grayscale-0" />
               <div className="absolute inset-0 bg-gradient-to-t from-zinc-950 via-transparent to-transparent opacity-80"></div>
               <div className="absolute bottom-4 left-4">
                 <p className="text-[10px] font-mono text-lime-400 mb-1">WRAP_GIFT</p>
                 <p className="font-bold text-sm">Custom Leatherwork</p>
               </div>
               <div className="absolute top-4 right-4 bg-zinc-950/50 p-2 rounded-full opacity-0 group-hover:opacity-100 transition-opacity">
                 <Maximize2 size={16} />
               </div>
            </div>
          </div>
        </div>
      </section>

      {/* --- WORKFLOW SECTION --- */}
      <section id="process" className="py-24 border-y border-zinc-800 bg-zinc-900">
        <div className="max-w-7xl mx-auto px-6">
            <div className="flex flex-col md:flex-row justify-between items-start md:items-end mb-16 gap-4">
                <div>
                    <h2 className="text-3xl font-bold mb-2 tracking-tight">THE WORKFLOW</h2>
                    <p className="text-zinc-400">Optimized for tight production schedules.</p>
                </div>
                <div className="flex items-center gap-2 text-xs font-mono text-zinc-500">
                    <Download size={12} />
                    DOWNLOAD_SPECS.PDF
                </div>
            </div>

            <div className="grid md:grid-cols-3 gap-0 border border-zinc-800 bg-zinc-950">
                {[
                    { step: "01", title: "UPLOAD BRIEF", desc: "Send artwork & deadline. We accept all standard production formats." },
                    { step: "02", title: "INSTANT PROOF", desc: "Receive a digital mock-up and quote within 2 business hours." },
                    { step: "03", title: "SET DELIVERY", desc: "We print and deliver directly to the production office or location." }
                ].map((item, i) => (
                    <div key={i} className="group relative p-8 md:border-r border-b md:border-b-0 border-zinc-800 last:border-0 hover:bg-zinc-900 transition-colors">
                        <div className="text-4xl font-black text-zinc-800 group-hover:text-lime-400 mb-6 transition-colors">
                            {item.step}
                        </div>
                        <h3 className="text-xl font-bold mb-2 tracking-tight">{item.title}</h3>
                        <p className="text-zinc-400 text-sm leading-relaxed">{item.desc}</p>
                        
                        <div className="absolute top-6 right-6 opacity-0 group-hover:opacity-20 transition-opacity text-lime-400">
                            <ScanLine size={48} strokeWidth={1} />
                        </div>
                    </div>
                ))}
            </div>
        </div>
      </section>

      {/* --- FOOTER CTA --- */}
      <section className="py-20 bg-zinc-950">
        <div className="max-w-4xl mx-auto px-6 text-center">
          <h2 className="text-4xl md:text-5xl font-bold mb-6 tracking-tight">DON'T LET A MISSING LOGO<br/>HOLD UP THE SHOOT.</h2>
          <p className="text-zinc-400 mb-8 max-w-lg mx-auto">Upload your art, set your deadline, and get back to managing the set. We'll handle the rest.</p>
          <button onClick={() => setIsQuoteOpen(true)} className="bg-white text-zinc-950 px-10 py-5 font-bold text-xl hover:bg-lime-400 transition-colors w-full md:w-auto rounded-sm">
            START YOUR ORDER
          </button>
          <div className="mt-8 flex items-center justify-center gap-2 text-zinc-500 text-sm font-mono">
            <Phone size={14} />
            <span>RUSH ORDERS: (555) 123-4567</span>
          </div>
        </div>
      </section>

      {/* --- WIZARD MODAL --- */}
      {isQuoteOpen && (
        <div className="fixed inset-0 z-[100] flex items-center justify-center p-4">
          <div className="absolute inset-0 bg-zinc-950/90 backdrop-blur-sm" onClick={() => setIsQuoteOpen(false)}></div>
          
          <div className="relative bg-zinc-900 border border-zinc-700 w-full max-w-lg shadow-2xl rounded-sm overflow-hidden flex flex-col min-h-[500px]">
            {/* Modal Header */}
            <div className="px-8 py-6 border-b border-zinc-800 flex justify-between items-center bg-zinc-900">
                <div>
                    <h3 className="text-xl font-bold tracking-tight uppercase">New Request</h3>
                    <div className="flex gap-1 mt-1">
                        {[1,2,3].map(step => (
                            <div key={step} className={`h-1 w-8 ${step <= wizardStep ? 'bg-lime-400' : 'bg-zinc-800'}`}></div>
                        ))}
                    </div>
                </div>
                <button onClick={() => setIsQuoteOpen(false)} className="text-zinc-500 hover:text-white transition-colors">
                    <X size={24} />
                </button>
            </div>

            {/* Modal Body */}
            <div className="p-8 flex-grow bg-zinc-900">
                {formSuccess ? (
                    <div className="text-center py-12">
                        <CheckCircle size={64} className="text-lime-400 mx-auto mb-6" />
                        <h3 className="text-2xl font-bold mb-2">RECEIVED.</h3>
                        <p className="text-zinc-400 mb-6 font-mono text-sm">Our producers are reviewing your brief. <br/>Check your email in ~2 hours.</p>
                        <div className="inline-block p-4 border border-zinc-800 bg-zinc-950 font-mono text-xs text-lime-400">
                            REF: {Math.floor(Math.random() * 100000)}
                        </div>
                    </div>
                ) : (
                    <>
                        {/* STEP 1: CATEGORY */}
                        {wizardStep === 1 && (
                            <div className="space-y-6">
                                <h4 className="font-mono text-xs text-zinc-500 uppercase tracking-widest">01 / CATEGORY</h4>
                                <h3 className="text-xl font-bold">What are we producing?</h3>
                                <div className="space-y-3">
                                    {['Crew Gear (Bulk)', 'Prop/Wardrobe (Custom)', 'Wrap Gifts (Premium)'].map((opt) => (
                                        <button 
                                            key={opt}
                                            onClick={() => { updateData('type', opt); handleNextStep(); }}
                                            className="w-full flex items-center justify-between p-4 border border-zinc-700 hover:border-lime-400 hover:bg-zinc-800 transition-all text-left group bg-zinc-950"
                                        >
                                            <span className="font-bold text-sm">{opt}</span>
                                            <ChevronRight className="text-zinc-700 group-hover:text-lime-400 transition-colors" size={16} />
                                        </button>
                                    ))}
                                </div>
                            </div>
                        )}

                        {/* STEP 2: DETAILS */}
                        {wizardStep === 2 && (
                            <div className="space-y-6">
                                <h4 className="font-mono text-xs text-zinc-500 uppercase tracking-widest">02 / SPECS</h4>
                                <h3 className="text-xl font-bold">Project Details</h3>
                                <div className="space-y-4">
                                    <div>
                                        <label className="block text-xs font-bold text-zinc-500 uppercase mb-2">Estimated Quantity</label>
                                        <input 
                                            type="number" 
                                            value={formData.quantity}
                                            onChange={(e) => updateData('quantity', e.target.value)}
                                            placeholder="e.g. 50"
                                            className="w-full bg-zinc-950 border border-zinc-700 p-4 text-zinc-100 focus:outline-none focus:border-lime-400 transition-colors rounded-sm font-mono text-sm"
                                            autoFocus
                                        />
                                    </div>
                                    <div>
                                        <label className="block text-xs font-bold text-zinc-500 uppercase mb-2">Hard Deadline</label>
                                        <input 
                                            type="date" 
                                            value={formData.deadline}
                                            onChange={(e) => updateData('deadline', e.target.value)}
                                            className="w-full bg-zinc-950 border border-zinc-700 p-4 text-zinc-100 focus:outline-none focus:border-lime-400 transition-colors rounded-sm font-mono text-sm uppercase"
                                        />
                                        <p className="text-xs text-lime-400/80 mt-2 flex items-center gap-1 font-mono">
                                            <Zap size={12}/> RUSH PRODUCTION AVAILABLE
                                        </p>
                                    </div>
                                </div>
                            </div>
                        )}

                        {/* STEP 3: CONTACT */}
                        {wizardStep === 3 && (
                            <div className="space-y-6">
                                <h4 className="font-mono text-xs text-zinc-500 uppercase tracking-widest">03 / CONTACT</h4>
                                <h3 className="text-xl font-bold">Where should we send the quote?</h3>
                                <div>
                                    <label className="block text-xs font-bold text-zinc-500 uppercase mb-2">Work Email</label>
                                    <input 
                                        type="email" 
                                        value={formData.email}
                                        onChange={(e) => updateData('email', e.target.value)}
                                        placeholder="producer@production.com"
                                        className="w-full bg-zinc-950 border border-zinc-700 p-4 text-zinc-100 focus:outline-none focus:border-lime-400 transition-colors rounded-sm font-mono text-sm"
                                        autoFocus
                                    />
                                </div>
                                <div className="flex items-start gap-3 p-4 border border-zinc-800 bg-zinc-950/50">
                                    <FileText className="text-lime-400 shrink-0 mt-1" size={16} />
                                    <p className="text-xs text-zinc-400 leading-relaxed">
                                        We respect production privacy. This data is encrypted and deleted if no order is placed within 30 days.
                                    </p>
                                </div>
                            </div>
                        )}
                    </>
                )}
            </div>

            {/* Modal Footer Controls */}
            {!formSuccess && (
                <div className="p-6 border-t border-zinc-800 flex justify-between bg-zinc-900">
                    {wizardStep > 1 ? (
                        <button onClick={handlePrevStep} className="text-zinc-500 hover:text-white px-4 py-2 font-bold text-sm uppercase tracking-wider transition-colors">
                            Back
                        </button>
                    ) : (
                        <div></div>
                    )}
                    
                    {wizardStep < 3 ? (
                        <button 
                            onClick={handleNextStep}
                            disabled={wizardStep === 1 && !formData.type}
                            className="bg-zinc-100 hover:bg-white text-zinc-900 px-6 py-3 font-bold text-sm transition-all disabled:opacity-50 disabled:cursor-not-allowed flex items-center gap-2 uppercase tracking-wider rounded-sm"
                        >
                            Next <ChevronRight size={16}/>
                        </button>
                    ) : (
                        <button 
                            onClick={submitForm}
                            className="bg-lime-400 hover:bg-lime-300 text-zinc-900 px-8 py-3 font-bold text-sm transition-all flex items-center gap-2 uppercase tracking-wider rounded-sm"
                        >
                            Submit Brief <CheckCircle size={16}/>
                        </button>
                    )}
                </div>
            )}
          </div>
        </div>
      )}
    </div>
  );
};

export default App;
