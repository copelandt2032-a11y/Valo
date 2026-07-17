import React, { useState, useEffect, useRef } from 'react';
import { 
  Sparkles, 
  Layers, 
  Wind, 
  MapPin, 
  Phone, 
  Clock, 
  Calendar, 
  Users, 
  ChevronRight, 
  Heart, 
  Wine, 
  Flame, 
  Compass, 
  ArrowRight,
  Maximize2,
  Droplet,
  Volume2,
  VolumeX,
  Thermometer,
  Eye,
  Settings,
  Sliders,
  Compass as CompassIcon,
  Compass as RadarIcon,
  HelpCircle,
  Database
} from 'lucide-react';

export default function App() {
  const [mobileMenuOpen, setMobileMenuOpen] = useState(false);
  const [isReservationOpen, setIsReservationOpen] = useState(false);
  const [activeMenuTab, setActiveMenuTab] = useState('firstSeeding');
  const [reservationStep, setReservationStep] = useState(1);
  const [bookingSuccess, setBookingSuccess] = useState(false);
  const [activeSection, setActiveSection] = useState('hero');
  
  // High-performance smooth scroll and velocity tracking
  const [smoothScrollProgress, setSmoothScrollProgress] = useState(0);
  const [smoothScrollY, setSmoothScrollY] = useState(0);
  const [scrollVelocity, setScrollVelocity] = useState(0);
  const [isScrolling, setIsScrolling] = useState(false);
  
  // Custom multi-ring tracking cursor coordinates
  const [mousePos, setMousePos] = useState({ x: 0, y: 0 });
  const [mouseSpeed, setMouseSpeed] = useState({ x: 0, y: 0 });
  const [customCursorPos, setCustomCursorPos] = useState({ x: -100, y: -100 });
  const [cursorHovering, setCursorHovering] = useState(false);

  // Atmospheric Light Overrides: 'fire' vs 'frost'
  const [globalTheme, setGlobalTheme] = useState('fire'); 
  const [isAmbientSoundOn, setIsAmbientSoundOn] = useState(false);

  // Seat Visualizer State
  const [selectedSeat, setSelectedSeat] = useState(0);

  // Localized 3D card tilt states
  const [tiltState, setTiltState] = useState({});
  const [selectedPairingDish, setSelectedPairingDish] = useState('reindeer');
  const [hoveredVaultPanel, setHoveredVaultPanel] = useState(null);
  
  // Vault Interactive Detail Panel states
  const [selectedVaultChamber, setSelectedVaultChamber] = useState('hearth');
  const [viewedChamberMetric, setViewedChamberMetric] = useState('schematic');

  // Alchemical Forge States
  const [forgeInventory, setForgeInventory] = useState([]);
  const [forgeOutcome, setForgeOutcome] = useState(null);

  // Vintage Timeline States
  const [selectedVintageYear, setSelectedVintageYear] = useState('2015');

  // Reservation data
  const [bookingData, setBookingData] = useState({
    date: '2026-10-12',
    time: '19:00',
    guests: '2',
    name: '',
    email: '',
    phone: '',
    dietary: '',
    specialRequest: '',
    agreedToTerms: false
  });

  const canvasRef = useRef(null);
  const alchemyCanvasRef = useRef(null);
  const vaultCanvasRef = useRef(null);
  const audioContextRef = useRef(null);
  const prevMousePos = useRef({ x: 0, y: 0 });
  const targetScrollY = useRef(0);
  const currentScrollY = useRef(0);
  const scrollTimeoutRef = useRef(null);

  // Web Audio Synthesizer Controller for high-end sensory feedback
  const playSoundEffect = (type) => {
    if (!isAmbientSoundOn) return;
    try {
      if (!audioContextRef.current) {
        audioContextRef.current = new (window.AudioContext || window.webkitAudioContext)();
      }
      const ctx = audioContextRef.current;
      if (ctx.state === 'suspended') {
        ctx.resume();
      }

      const osc = ctx.createOscillator();
      const gainNode = ctx.createGain();
      osc.connect(gainNode);
      gainNode.connect(ctx.destination);

      if (type === 'hover') {
        // Crystalline, ultra-light chime
        const baseFreq = globalTheme === 'frost' ? 880 : 440;
        osc.type = 'triangle';
        osc.frequency.setValueAtTime(baseFreq, ctx.currentTime);
        osc.frequency.exponentialRampToValueAtTime(baseFreq * 1.5, ctx.currentTime + 0.15);
        gainNode.gain.setValueAtTime(0.008, ctx.currentTime);
        gainNode.gain.exponentialRampToValueAtTime(0.0001, ctx.currentTime + 0.18);
        osc.start();
        osc.stop(ctx.currentTime + 0.18);
      } else if (type === 'click') {
        // Warm, resonant string tap
        const baseFreq = globalTheme === 'frost' ? 330 : 220;
        osc.type = 'sine';
        osc.frequency.setValueAtTime(baseFreq, ctx.currentTime);
        osc.frequency.exponentialRampToValueAtTime(baseFreq * 0.5, ctx.currentTime + 0.25);
        gainNode.gain.setValueAtTime(0.04, ctx.currentTime);
        gainNode.gain.exponentialRampToValueAtTime(0.0001, ctx.currentTime + 0.3);
        osc.start();
        osc.stop(ctx.currentTime + 0.3);
      } else if (type === 'forge') {
        // Deep alchemical bubbling rumble and flash
        osc.type = 'sawtooth';
        osc.frequency.setValueAtTime(110, ctx.currentTime);
        osc.frequency.linearRampToValueAtTime(220, ctx.currentTime + 0.5);
        gainNode.gain.setValueAtTime(0.03, ctx.currentTime);
        gainNode.gain.exponentialRampToValueAtTime(0.0001, ctx.currentTime + 0.6);
        osc.start();
        osc.stop(ctx.currentTime + 0.6);
      }
    } catch (e) {
      console.warn('Audio Context block:', e);
    }
  };

  const handleTiltMove = (e, elementId) => {
    const rect = e.currentTarget.getBoundingClientRect();
    const x = e.clientX - rect.left; 
    const y = e.clientY - rect.top;  
    const xc = rect.width / 2;
    const yc = rect.height / 2;
    const rotateY = ((x - xc) / xc) * 16; 
    const rotateX = ((yc - y) / yc) * 16; 
    setTiltState(prev => ({
      ...prev,
      [elementId]: { x: rotateX, y: rotateY, shineX: (x / rect.width) * 100, shineY: (y / rect.height) * 100 }
    }));
  };

  const handleTiltLeave = (elementId) => {
    setTiltState(prev => ({
      ...prev,
      [elementId]: { x: 0, y: 0, shineX: 50, shineY: 50 }
    }));
  };

  useEffect(() => {
    const handleScrollEvent = () => {
      targetScrollY.current = window.scrollY;
      setIsScrolling(true);
      if (scrollTimeoutRef.current) clearTimeout(scrollTimeoutRef.current);
      scrollTimeoutRef.current = setTimeout(() => {
        setIsScrolling(false);
      }, 250);
    };

    window.addEventListener('scroll', handleScrollEvent, { passive: true });

    let animationFrameId;
    const updateLerpedScroll = () => {
      const damping = 0.075; 
      const diff = targetScrollY.current - currentScrollY.current;
      const velocity = Math.abs(diff);
      setScrollVelocity(velocity);
      
      currentScrollY.current += diff * damping;
      
      if (Math.abs(targetScrollY.current - currentScrollY.current) < 0.1) {
        currentScrollY.current = targetScrollY.current;
      }

      setSmoothScrollY(currentScrollY.current);

      const totalHeight = document.documentElement.scrollHeight - window.innerHeight;
      if (totalHeight > 0) {
        setSmoothScrollProgress(currentScrollY.current / totalHeight);
      }

      // Check active sections dynamically as we scroll
      const sections = ['hero', 'philosophy', 'menu', 'forge', 'vault', 'cellar', 'tablemap', 'chef', 'experiences', 'testimonials', 'reserve'];
      for (const section of sections) {
        const el = document.getElementById(section);
        if (el) {
          const rect = el.getBoundingClientRect();
          if (rect.top <= window.innerHeight * 0.45 && rect.bottom >= window.innerHeight * 0.45) {
            setActiveSection(section);
          }
        }
      }

      animationFrameId = requestAnimationFrame(updateLerpedScroll);
    };

    updateLerpedScroll();

    return () => {
      window.removeEventListener('scroll', handleScrollEvent);
      cancelAnimationFrame(animationFrameId);
      if (scrollTimeoutRef.current) clearTimeout(scrollTimeoutRef.current);
    };
  }, []);

  useEffect(() => {
    const observerOptions = {
      root: null,
      rootMargin: '0px',
      threshold: 0.1
    };

    const revealCallback = (entries) => {
      entries.forEach((entry) => {
        if (entry.isIntersecting) {
          entry.target.classList.add('reveal-active');
        }
      });
    };

    const observer = new IntersectionObserver(revealCallback, observerOptions);
    const elementsToReveal = document.querySelectorAll('.reveal-on-scroll');
    elementsToReveal.forEach((el) => observer.observe(el));

    return () => {
      elementsToReveal.forEach((el) => observer.unobserve(el));
    };
  }, []);

  useEffect(() => {
    const handleMouseMove = (e) => {
      const normalizedX = (e.clientX / window.innerWidth - 0.5) * 2;
      const normalizedY = (e.clientY / window.innerHeight - 0.5) * 2;
      
      setMousePos({ x: normalizedX, y: normalizedY });
      
      const dx = e.clientX - prevMousePos.current.x;
      const dy = e.clientY - prevMousePos.current.y;
      setMouseSpeed({ x: dx * 0.15, y: dy * 0.15 });
      
      prevMousePos.current = { x: e.clientX, y: e.clientY };
      setCustomCursorPos({ x: e.clientX, y: e.clientY });
    };

    window.addEventListener('mousemove', handleMouseMove, { passive: true });
    return () => {
      window.removeEventListener('mousemove', handleMouseMove);
    };
  }, []);

  useEffect(() => {
    const canvas = canvasRef.current;
    if (!canvas) return;
    const ctx = canvas.getContext('2d');
    let animationFrameId;

    const resizeCanvas = () => {
      canvas.width = window.innerWidth;
      canvas.height = window.innerHeight;
    };
    resizeCanvas();
    window.addEventListener('resize', resizeCanvas);

    const particles = [];
    const maxParticles = 140;

    class GlobalAtmosphereParticle {
      constructor() {
        this.reset();
        this.y = Math.random() * canvas.height;
      }
      reset() {
        this.x = Math.random() * canvas.width;
        this.y = canvas.height + Math.random() * 80;
        this.size = Math.random() * 2.8 + 0.6;
        this.speedY = Math.random() * 1.5 + 0.4;
        this.speedX = Math.random() * 0.9 - 0.45;
        this.opacity = Math.random() * 0.85 + 0.15;
        this.sinOffset = Math.random() * Math.PI * 2;
        this.sinSpeed = Math.random() * 0.02 + 0.005;
        this.brightnessFactor = 1;
        this.spinAngle = Math.random() * Math.PI * 2;
        this.spinSpeed = Math.random() * 0.05 - 0.025;
      }
      update(currentScrollVelocity, theme) {
        const dx = this.x - prevMousePos.current.x;
        const dy = this.y - prevMousePos.current.y;
        const dist = Math.sqrt(dx * dx + dy * dy);
        const repelRadius = 160;

        if (dist < repelRadius) {
          const force = (repelRadius - dist) / repelRadius;
          this.x += (dx / dist) * force * 5.5;
          this.y += (dy / dist) * force * 4.0;
          this.brightnessFactor = 2.2;
          this.size = Math.min(this.size + 0.2, 4.5);
        } else {
          this.brightnessFactor = Math.max(1, this.brightnessFactor - 0.025);
        }

        this.x += mouseSpeed.x * 0.15;
        const thermalUpdraft = currentScrollVelocity * 0.1;
        this.y -= (this.speedY + thermalUpdraft);
        
        this.sinOffset += this.sinSpeed;
        this.x += this.speedX + Math.sin(this.sinOffset) * 0.35;
        this.opacity -= 0.0015;
        this.spinAngle += this.spinSpeed;

        if (this.y < -35 || this.opacity <= 0) {
          this.reset();
        }
      }
      draw(theme) {
        ctx.save();
        ctx.globalAlpha = this.opacity;
        
        if (theme === 'fire') {
          const hue = Math.random() > 0.55 ? 42 : 21; 
          ctx.shadowBlur = this.size * 6.0 * this.brightnessFactor;
          ctx.shadowColor = `hsl(${hue}, 92%, 52%)`;
          ctx.fillStyle = `hsl(${hue}, 98%, ${68 * this.brightnessFactor}%)`;
          ctx.beginPath();
          ctx.arc(this.x, this.y, this.size, 0, Math.PI * 2);
          ctx.fill();
        } else {
          ctx.shadowBlur = this.size * 5.0 * this.brightnessFactor;
          ctx.shadowColor = `rgba(160, 215, 255, 0.75)`;
          ctx.fillStyle = `rgba(215, 240, 255, ${0.85 * this.brightnessFactor})`;
          ctx.beginPath();
          ctx.translate(this.x, this.y);
          ctx.rotate(this.spinAngle);
          for (let i = 0; i < 4; i++) {
            ctx.lineTo(0, this.size * 1.6);
            ctx.lineTo(this.size * 0.45, 0);
            ctx.rotate(Math.PI / 2);
          }
          ctx.closePath();
          ctx.fill();
        }
        ctx.restore();
      }
    }

    for (let i = 0; i < maxParticles; i++) {
      particles.push(new GlobalAtmosphereParticle());
    }

    const animate = () => {
      ctx.clearRect(0, 0, canvas.width, canvas.height);
      particles.forEach((p) => {
        p.update(scrollVelocity, globalTheme);
        p.draw(globalTheme);
      });
      animationFrameId = requestAnimationFrame(animate);
    };
    animate();

    return () => {
      window.removeEventListener('resize', resizeCanvas);
      cancelAnimationFrame(animationFrameId);
    };
  }, [mouseSpeed, scrollVelocity, globalTheme]);

  useEffect(() => {
    const canvas = alchemyCanvasRef.current;
    if (!canvas) return;
    const ctx = canvas.getContext('2d');
    let animationFrameId;

    const resizeCanvas = () => {
      const rect = canvas.getBoundingClientRect();
      canvas.width = rect.width * window.devicePixelRatio;
      canvas.height = rect.height * window.devicePixelRatio;
      ctx.scale(window.devicePixelRatio, window.devicePixelRatio);
    };
    resizeCanvas();
    window.addEventListener('resize', resizeCanvas);

    const particles = [];
    const maxParticles = 95;

    class AlchemyEssence {
      constructor() {
        this.reset();
        this.y = Math.random() * (canvas.height / window.devicePixelRatio);
      }
      reset() {
        const w = canvas.width / window.devicePixelRatio;
        const h = canvas.height / window.devicePixelRatio;
        this.centerX = w / 2;
        this.centerY = h / 2;
        this.radius = Math.random() * Math.min(w, h) * 0.42 + 25;
        this.angle = Math.random() * Math.PI * 2;
        this.angularSpeed = (Math.random() * 0.018 + 0.005) * (Math.random() > 0.5 ? 1 : -1);
        this.radialSpeed = Math.random() * 0.35 - 0.175;
        this.size = Math.random() * 2.2 + 0.8;
        this.opacity = Math.random() * 0.85 + 0.15;
        
        if (globalTheme === 'frost') {
          this.hue = Math.random() > 0.5 ? 202 : 228;
          this.saturation = 85;
          this.lightness = 76;
        } else {
          if (activeMenuTab === 'firstSeeding') {
            this.hue = Math.random() > 0.5 ? 42 : 112; 
            this.saturation = 88;
            this.lightness = 62;
          } else if (activeMenuTab === 'elementalFire') {
            this.hue = Math.random() * 20 + 14; 
            this.saturation = 98;
            this.lightness = 57;
          } else {
            this.hue = Math.random() > 0.65 ? 202 : 42; 
            this.saturation = Math.random() > 0.6 ? 92 : 22;
            this.lightness = 77;
          }
        }
        
        this.depthZ = Math.random() * 2.2 - 1.1; 
      }
      update(vel) {
        const scrollImpact = 1 + (vel * 0.09);
        this.angle += this.angularSpeed * scrollImpact;
        this.radius += this.radialSpeed + (Math.sin(this.angle * 2) * 0.12);
        
        const targetX = this.centerX + Math.cos(this.angle) * this.radius + (mousePos.x * 28 * this.depthZ);
        const targetY = this.centerY + Math.sin(this.angle) * this.radius + (mousePos.y * 28 * this.depthZ);
        
        this.x = targetX;
        this.y = targetY;
        
        this.opacity -= 0.0024;
        this.size = Math.max(0.12, this.size * 0.994);

        if (this.opacity <= 0 || this.radius < 4) {
          this.reset();
        }
      }
      draw() {
        ctx.save();
        ctx.globalAlpha = this.opacity;
        
        const scaleFactor = 1 + (this.depthZ * 0.38);
        
        ctx.shadowBlur = this.size * 6.5 * scaleFactor;
        ctx.shadowColor = `hsl(${this.hue}, ${this.saturation}%, ${this.lightness}%)`;
        ctx.fillStyle = `hsl(${this.hue}, ${this.saturation}%, ${this.lightness + 12}%)`;
        
        ctx.beginPath();
        ctx.arc(this.x, this.y, this.size * scaleFactor, 0, Math.PI * 2);
        ctx.fill();
        ctx.restore();
      }
    }

    for (let i = 0; i < maxParticles; i++) {
      particles.push(new AlchemyEssence());
    }

    const animate = () => {
      ctx.clearRect(0, 0, canvas.width / window.devicePixelRatio, canvas.height / window.devicePixelRatio);
      particles.forEach((p) => {
        p.update(scrollVelocity);
        p.draw();
      });
      animationFrameId = requestAnimationFrame(animate);
    };
    animate();

    return () => {
      window.removeEventListener('resize', resizeCanvas);
      cancelAnimationFrame(animationFrameId);
    };
  }, [activeMenuTab, mousePos, scrollVelocity, globalTheme]);

  useEffect(() => {
    const canvas = vaultCanvasRef.current;
    if (!canvas) return;
    const ctx = canvas.getContext('2d');
    let animationFrameId;

    const resizeCanvas = () => {
      const rect = canvas.getBoundingClientRect();
      canvas.width = rect.width * window.devicePixelRatio;
      canvas.height = rect.height * window.devicePixelRatio;
      ctx.scale(window.devicePixelRatio, window.devicePixelRatio);
    };
    resizeCanvas();
    window.addEventListener('resize', resizeCanvas);

    const fluidLines = [];
    const maxLines = 15;

    class ThermodynamicCurvingWind {
      constructor() {
        this.reset();
        this.y = Math.random() * (canvas.height / window.devicePixelRatio);
      }
      reset() {
        const w = canvas.width / window.devicePixelRatio;
        const h = canvas.height / window.devicePixelRatio;
        this.points = [];
        this.maxLength = Math.random() * 120 + 80;
        this.x = -20;
        this.y = Math.random() * h;
        this.amplitude = Math.random() * 30 + 10;
        this.frequency = Math.random() * 0.015 + 0.005;
        this.speedX = Math.random() * 1.5 + 1.0;
        this.phase = Math.random() * Math.PI * 2;
        this.opacity = Math.random() * 0.5 + 0.1;
        this.color = selectedVaultChamber === 'hearth' || selectedVaultChamber === 'chimney'
          ? `hsla(${Math.random() > 0.5 ? 42 : 21}, 95%, 60%, ${this.opacity})`
          : `hsla(${Math.random() > 0.5 ? 202 : 180}, 90%, 80%, ${this.opacity})`;
        this.lineWidth = Math.random() * 1.5 + 0.5;
      }
      update() {
        this.x += this.speedX;
        this.phase += 0.02;
        this.y += Math.sin(this.x * this.frequency + this.phase) * 0.35;
        
        this.points.push({ x: this.x, y: this.y });
        if (this.points.length > this.maxLength) {
          this.points.shift();
        }

        const w = canvas.width / window.devicePixelRatio;
        if (this.x > w + 20 || this.points.length === 0) {
          this.reset();
        }
      }
      draw() {
        if (this.points.length < 2) return;
        ctx.save();
        ctx.beginPath();
        ctx.moveTo(this.points[0].x, this.points[0].y);
        for (let i = 1; i < this.points.length; i++) {
          ctx.lineTo(this.points[i].x, this.points[i].y);
        }
        ctx.lineWidth = this.lineWidth;
        ctx.strokeStyle = this.color;
        ctx.shadowBlur = this.lineWidth * 3.5;
        ctx.shadowColor = this.color;
        ctx.lineCap = 'round';
        ctx.stroke();
        ctx.restore();
      }
    }

    for (let i = 0; i < maxLines; i++) {
      fluidLines.push(new ThermodynamicCurvingWind());
    }

    const animate = () => {
      ctx.clearRect(0, 0, canvas.width / window.devicePixelRatio, canvas.height / window.devicePixelRatio);
      fluidLines.forEach((l) => {
        l.update();
        l.draw();
      });
      animationFrameId = requestAnimationFrame(animate);
    };
    animate();

    return () => {
      window.removeEventListener('resize', resizeCanvas);
      cancelAnimationFrame(animationFrameId);
    };
  }, [selectedVaultChamber]);

  const rawIngredients = [
    { id: 'sap', label: 'Birch Sap', desc: 'Slightly sweet, dynamic spring extract tapped from high birches.' },
    { id: 'juniper', label: 'Wild Juniper', desc: 'Highly aromatic, hand-plucked dark woodland pine berries.' },
    { id: 'kelp', label: 'Shoreline Kelp', desc: 'Saline-dense, ocean-slick giant seaweed cured on embers.' },
    { id: 'smoke', label: 'Alder Wood Smoke', desc: 'Dense aromatic timber exhaust captured in clay vessels.' },
    { id: 'lichens', label: 'Frozen Lichens', desc: 'Crisp mountain rock growths recovered beneath the deep frost.' }
  ];

  const handleIngredientToggle = (id) => {
    playSoundEffect('hover');
    setForgeOutcome(null);
    if (forgeInventory.includes(id)) {
      setForgeInventory(prev => prev.filter(item => item !== id));
    } else {
      if (forgeInventory.length >= 3) {
        setForgeInventory(prev => [...prev.slice(1), id]);
      } else {
        setForgeInventory(prev => [...prev, id]);
      }
    }
  };

  const executeAlchemyForge = () => {
    playSoundEffect('forge');
    if (forgeInventory.length < 2) {
      setForgeOutcome({
        title: "Insufficient Elements",
        desc: "You must mix at least 2 wild botanicals inside the hearth to create a recipe."
      });
      return;
    }

    const inventoryKey = [...forgeInventory].sort().join('+');
    
    const recipes = {
      'sap+smoke': {
        title: 'Heated Birch Nectar',
        desc: 'A smoky, comforting spring syrup reduction featuring rich woody caramel undertones.'
      },
      'juniper+sap': {
        title: 'Arctic Canopy Elixir',
        desc: 'A medicinal, refreshing forest extract combining sweet tree-blood with intense alpine juniper oils.'
      },
      'kelp+smoke': {
        title: 'Seaside Ember Decanter',
        desc: 'An intense, highly savory broth replicating the wild winds and salt-baked tides of the northern fjords.'
      },
      'juniper+kelp': {
        title: 'Shoreline Foraged Shrub',
        desc: 'A balanced tonic that carries high marine minerals offset by aromatic mountain berry seeds.'
      },
      'lichens+sap': {
        title: 'Glacial Lichen Candy',
        desc: 'A completely unique crystalline crisp bite, preserved inside mountain birch sugars.'
      },
      'lichens+smoke': {
        title: 'Scorched Rock Moss',
        desc: 'A highly structural, aromatic plate crunch used by Chef Elina to dress game venison.'
      }
    };

    const match = recipes[inventoryKey] || {
      title: 'VALO Wild Herbal Infusion',
      desc: 'A highly adaptive, aromatic infusion carrying the natural, untamed essence of Mayfair\'s Nordic forest supply.'
    };

    setForgeOutcome(match);
  };

  const seatsData = [
    { name: "The Forge Master Seat", pos: "Seat 1 (Direct Hearth View)", desc: "Directly faces our roaring 400°C charcoal spit. Enjoy dramatic flames, heat-shimmers, and personal handovers from Chef Elina." },
    { name: "The Carver's Alcove", pos: "Seat 4 (Slicing Board View)", desc: "Observe the complex structural carving, skin-basting, and plating of Shetland scallops and Cairngorms venison." },
    { name: "The Sommelier Corner", pos: "Seat 7 (Subterranean Access)", desc: "Positioned adjacent to our subterranean passage, allowing lightning-fast, ice-cold deliveries of custom meads and natural wines." },
    { name: "The Whisper Seating", pos: "Seat 10 (Quiet Timber Wing)", desc: "An acoustically dampened zone framed by thick charred timbers. Ideal for romantic, focused sensory exploration." }
  ];

  const vintageReserves = {
    '2012': { name: "Radikon 'Jakot' Friulano Amber", region: "Oslavia, Italy", notes: "Deep prolong skin contact, intense orange peel, dried pine leaves, and rich complex tannins.", stock: "Only 14 bottles remaining" },
    '2015': { name: "Cold-Pressed Cloudberry Mead", region: "Troms, Norway", notes: "Fermented wild mountain honey, distinct sub-zero arctic acidity, crisp botanical nose.", stock: "Only 6 bottles remaining in reserve cellar" },
    '2018': { name: "Gut Oggau 'Theodora' Weiss", region: "Burgenland, Austria", notes: "Chalky soil minerals, unfiltered biodynamic grape must, sharp citrus zest.", stock: "28 bottles aging in stone jars" },
    '2022': { name: "VALO Foraged Pine Shoot Distillate", region: "Shetland Islands", notes: "Intense evergreen resins, hand-distilled pine pollen, extremely clean crisp finish.", stock: "Limited allocation on tasting seatings" }
  };

  const vaultChambersData = {
    hearth: {
      title: "The Mayfair Embers Core",
      subtitle: "Thermodynamic Hearth Core",
      temp: "420°C Thermal Maximum",
      humidity: "8% Relative Dryness",
      fuel: "Scots Pine & Dried Silver Birch",
      smoke: "Medium Alderwood Infusions",
      maturation: "Direct Spits, 12-hour charcoal curing cycles",
      profile: { umami: 95, acidic: 20, bitter: 55, aromatic: 85 },
      technicalNotes: "Engineered inside Mayfair using multi-layered, air-cooled insulation chambers. This enables roaring 400°C split fires without heating adjacent dining coordinates, creating localized convective hot-zones directly facing the sommelier counter.",
      chefRecommendation: "Perfect for rapid skin-searing on Diver Scallops to trap maritime juices before introducing parsnip emulsion."
    },
    scallop: {
      title: "Cryogenic Volcanic Stone Casing",
      subtitle: "Plated Thermal Chamber",
      temp: "4°C Controlled Shell Temperature",
      humidity: "78% Relative Moisture",
      fuel: "Basalt Rock Cooling Plinths",
      smoke: "None (Raw Maritime Focus)",
      maturation: "Instant deep-chill setting chambers",
      profile: { umami: 45, acidic: 90, bitter: 10, aromatic: 70 },
      technicalNotes: "Volcanic basalt stones are recovered from Northern Icelandic quarries and hollowed manually. These rocks are sub-zero conditioned before meal handovers. Hot dishes served inside these shells cool down exponentially at the point of contact, altering protein viscosity.",
      chefRecommendation: "We set raw hand-plucked juniper berries in these stones to force the instant release of highly volatile pine-resins."
    },
    chimney: {
      title: "Tactical Charcoal Aging Cells",
      subtitle: "Aerosol Infusion Chimneys",
      temp: "110°C Low Constant Thermal",
      humidity: "45% Medium Dryness",
      fuel: "Peat-Slick Cured Charcoal",
      smoke: "Dense Dry Alderwood Shards",
      maturation: "72-hour slow cold-smoke cascades",
      profile: { umami: 80, acidic: 40, bitter: 70, aromatic: 95 },
      technicalNotes: "A series of continuous subterranean chimneys designed to pull smoke down away from diners and across a network of cold-aging hooks. This slow vacuum-assisted ventilation coats venison cutlets in rich tar oils and forest soot molecules without over-cooking deep interior fibers.",
      chefRecommendation: "Recommended for curing the wild boar rack before transferring to direct flame grills."
    }
  };

  const handleBookingInputChange = (e) => {
    const { name, value, type, checked } = e.target;
    setBookingData(prev => ({
      ...prev,
      [name]: type === 'checkbox' ? checked : value
    }));
  };

  const handleNextStep = () => {
    playSoundEffect('click');
    if (reservationStep === 1) {
      setReservationStep(2);
    } else if (reservationStep === 2) {
      if (!bookingData.name || !bookingData.email || !bookingData.phone) return;
      setReservationStep(3);
    }
  };

  const handlePrevStep = () => {
    playSoundEffect('click');
    if (reservationStep > 1) {
      setReservationStep(prev => prev - 1);
    }
  };

  const handleConfirmBooking = (e) => {
    e.preventDefault();
    playSoundEffect('forge');
    setBookingSuccess(true);
  };

  const resetBookingForm = () => {
    playSoundEffect('click');
    setReservationStep(1);
    setBookingSuccess(false);
    setIsReservationOpen(false);
    setBookingData({
      date: '2026-10-12',
      time: '19:00',
      guests: '2',
      name: '',
      email: '',
      phone: '',
      dietary: '',
      specialRequest: '',
      agreedToTerms: false
    });
  };

  const scrollToSection = (id) => {
    playSoundEffect('click');
    const element = document.getElementById(id);
    if (element) {
      element.scrollIntoView({ behavior: 'smooth' });
    }
    setMobileMenuOpen(false);
  };

  return (
    <div className={`bg-[#0c0b0a] text-[#f4f3f0] min-h-screen font-sans selection:bg-[#d4a853] selection:text-[#0c0b0a] overflow-x-hidden antialiased relative transition-colors duration-1000 ${
      globalTheme === 'frost' ? 'theme-frost-active' : 'theme-fire-active'
    }`}>
      
      {/* 8K Ambient Physics Spark Engine Backing Canvas */}
      <canvas 
        ref={canvasRef} 
        className="fixed inset-0 pointer-events-none z-10 opacity-75"
      />

      {/* Cinematic Custom Interaction Follow-trail cursor */}
      <div 
        className={`hidden lg:block fixed w-12 h-12 rounded-full border pointer-events-none z-[9999] transition-all duration-150 ease-out -translate-x-1/2 -translate-y-1/2 ${
          cursorHovering 
            ? 'scale-[1.8] bg-[#d4a853]/15 shadow-[0_0_25px_rgba(212,168,83,0.4)] border-[#d4a853]' 
            : globalTheme === 'frost'
              ? 'border-blue-400/50 shadow-[0_0_10px_rgba(147,197,253,0.3)]'
              : 'border-[#d4a853]/60'
        }`}
        style={{ left: `${customCursorPos.x}px`, top: `${customCursorPos.y}px` }}
      >
        <svg className="w-full h-full rotate-[-90deg]" viewBox="0 0 100 100">
          <circle 
            cx="50" 
            cy="50" 
            r="44" 
            stroke={globalTheme === 'frost' ? '#60a5fa' : '#d4a853'} 
            strokeWidth="3" 
            fill="transparent" 
            strokeDasharray="276"
            strokeDashoffset={276 - (276 * smoothScrollProgress)}
            className="transition-all"
            opacity="0.8"
          />
        </svg>
      </div>
      <div 
        className={`hidden lg:block fixed w-3 h-3 rounded-full pointer-events-none z-[9999] -translate-x-1/2 -translate-y-1/2 transition-transform duration-100 ${
          cursorHovering ? 'scale-0' : 'scale-100'
        } ${globalTheme === 'frost' ? 'bg-gradient-to-tr from-blue-300 to-white' : 'bg-gradient-to-tr from-[#d4a853] to-[#ffda85]'}`}
        style={{ left: `${customCursorPos.x}px`, top: `${customCursorPos.y}px` }}
      />

      {/* Embedded High-Fidelity Custom Styling Rules */}
      <style>{`
        @import url('https://fonts.googleapis.com/css2?family=Cormorant+Garamond:ital,wght@0,400;0,600;0,700;1,400;1,600&family=Inter:wght@300;400;500;600&display=swap');
        
        .font-serif-cormorant {
          font-family: 'Cormorant Garamond', serif;
        }
        
        .font-sans-inter {
          font-family: 'Inter', sans-serif;
        }

        @keyframes marquee {
          0% { transform: translateX(0%); }
          100% { transform: translateX(-50%); }
        }

        .animate-marquee {
          display: flex;
          width: max-content;
          animation: marquee 25s linear infinite;
        }

        ::-webkit-scrollbar {
          width: 8px;
        }
        ::-webkit-scrollbar-track {
          background: #0c0b0a;
        }
        ::-webkit-scrollbar-thumb {
          background: #1c1a18;
          border-radius: 4px;
        }
        ::-webkit-scrollbar-thumb:hover {
          background: #d4a853;
        }

        /* HARDWARE ACCELERATED SCROLL REVEAL STYLES */
        .reveal-on-scroll {
          opacity: 0;
          transform: translateY(45px) scale(0.98);
          filter: blur(5px);
          transition: opacity 1.1s cubic-bezier(0.16, 1, 0.3, 1),
                      transform 1.1s cubic-bezier(0.16, 1, 0.3, 1),
                      filter 1.1s cubic-bezier(0.16, 1, 0.3, 1);
          will-change: transform, opacity, filter;
        }

        .reveal-on-scroll.reveal-active {
          opacity: 1;
          transform: translateY(0) scale(1);
          filter: blur(0px);
        }

        /* STEREOSCOPIC PARALLAX FRAME GLASS */
        .parallax-frame-container {
          position: relative;
          overflow: hidden;
          background: #121110;
        }

        .parallax-frame-container::before {
          content: '';
          position: absolute;
          inset: 0;
          border: 1px solid rgba(212, 168, 83, 0.15);
          pointer-events: none;
          z-index: 25;
          box-shadow: inset 0 0 25px rgba(0, 0, 0, 0.6);
        }

        .theme-frost-active .parallax-frame-container::before {
          border-color: rgba(147, 197, 253, 0.2);
        }

        .hologram-shine {
          position: absolute;
          top: 0;
          left: 0;
          width: 100%;
          height: 100%;
          background: radial-gradient(circle at var(--shine-x, 50%) var(--shine-y, 50%), rgba(255, 234, 159, 0.15) 0%, transparent 60%);
          pointer-events: none;
          z-index: 20;
          mix-blend-mode: color-dodge;
        }

        .theme-frost-active .hologram-shine {
          background: radial-gradient(circle at var(--shine-x, 50%) var(--shine-y, 50%), rgba(191, 219, 254, 0.25) 0%, transparent 60%);
        }

        .premium-glow-border {
          position: relative;
        }
        .premium-glow-border::after {
          content: '';
          position: absolute;
          inset: 0;
          border: 1px solid rgba(212, 168, 83, 0.08);
          transition: border-color 0.4s ease, box-shadow 0.4s ease;
          pointer-events: none;
        }
        .premium-glow-border:hover::after {
          border-color: rgba(212, 168, 83, 0.4);
          box-shadow: 0 0 25px rgba(212, 168, 83, 0.12);
        }

        .theme-frost-active .premium-glow-border:hover::after {
          border-color: rgba(147, 197, 253, 0.45);
          box-shadow: 0 0 25px rgba(147, 197, 253, 0.15);
        }

        @keyframes soundwave {
          0%, 100% { height: 4px; }
          50% { height: 18px; }
        }
        .soundwave-bar {
          animation: soundwave 0.8s ease-in-out infinite;
        }
        .soundwave-bar:nth-child(2) { animation-delay: 0.15s; }
        .soundwave-bar:nth-child(3) { animation-delay: 0.3s; }
        .soundwave-bar:nth-child(4) { animation-delay: 0.45s; }
      `}</style>

      {/* Floating Micro-Header and Ambient dial controls */}
      <header className="fixed top-0 left-0 w-full z-50 transition-all duration-300">
        <div className="bg-[#1c1813] border-b border-[#d4a853]/30 text-[10px] font-sans-inter font-light text-[#f4f3f0] tracking-[0.25em] uppercase py-2.5 text-center select-none relative z-10 backdrop-blur-md bg-opacity-95 shadow-[0_2px_15px_rgba(212,168,83,0.15)] flex justify-center items-center gap-6">
          <span>Open Wed–Sun · 17:30–23:30 · +44 20 8987 6543 · 42 Bruton Place, Mayfair</span>
          <div className="absolute top-0 right-0 left-0 h-[1px] bg-gradient-to-r from-transparent via-[#d4a853] to-transparent"></div>
        </div>

        <nav className="transition-all duration-300 py-4 px-6 lg:px-12">
          <div className="max-w-7xl mx-auto h-16 flex items-center justify-between">
            
            {/* Wordmark Logo */}
            <a 
              href="#hero" 
              onClick={(e) => { e.preventDefault(); scrollToSection('hero'); }} 
              className="flex flex-col items-start group relative bg-[#1c1813] border border-[#d4a853]/50 px-5 py-2.5 rounded-full backdrop-blur-md shadow-[0_4px_15px_rgba(212,168,83,0.15)] hover:border-[#d4a853] transition-all"
              onMouseEnter={() => { setCursorHovering(true); playSoundEffect('hover'); }}
              onMouseLeave={() => setCursorHovering(false)}
            >
              <span className="font-serif-cormorant text-2xl italic font-bold tracking-widest text-[#d4a853] transition-colors duration-300 group-hover:text-white">
                VALO
              </span>
              <span className="font-sans-inter text-[7px] tracking-[0.3em] uppercase text-[#a8a19a] -mt-0.5">
                Nordic Hearth & Forge
              </span>
            </a>

            {/* Desktop Navigation Links: Premium Oval Tabs (Standing out visually) */}
            <div className="hidden md:flex items-center space-x-3 bg-[#1c1813]/95 border border-[#d4a853]/40 p-1.5 rounded-full backdrop-blur-md shadow-[0_4px_25px_rgba(212,168,83,0.2)]">
              {[
                { id: 'menu', label: 'The Alchemy' },
                { id: 'forge', label: 'Wild Lab' },
                { id: 'vault', label: '3D Vault' },
                { id: 'cellar', label: 'Obsidian Cellar' },
                { id: 'tablemap', label: 'Hearth Table' },
                { id: 'chef', label: 'The Pioneer' }
              ].map((item) => (
                <button 
                  key={item.id}
                  onClick={() => scrollToSection(item.id)} 
                  className={`px-4 py-2 rounded-full font-sans-inter text-[11px] tracking-[0.18em] uppercase transition-all duration-300 ${
                    activeSection === item.id 
                      ? 'bg-gradient-to-r from-[#d4a853] to-[#bda043] text-[#0c0b0a] font-bold shadow-[0_2px_10px_rgba(212,168,83,0.3)]' 
                      : 'text-[#f4f3f0] hover:bg-[#d4a853]/10 hover:text-[#d4a853]'
                  }`}
                  onMouseEnter={() => { setCursorHovering(true); playSoundEffect('hover'); }}
                  onMouseLeave={() => setCursorHovering(false)}
                >
                  {item.label}
                </button>
              ))}
            </div>

            {/* CTA Seating Register Button & Premium Sound/Theme Controller */}
            <div className="hidden md:flex items-center space-x-4">
              
              {/* Dynamic Sound Ambience Simulator Widget */}
              <button
                onClick={() => { setIsAmbientSoundOn(!isAmbientSoundOn); playSoundEffect('click'); }}
                className="p-3 rounded-full border border-[#d4a853]/30 bg-[#121110] text-[#d4a853] hover:text-white hover:border-[#d4a853] transition-all flex items-center justify-center relative"
                title="Toggle Ambient Sounds"
              >
                {isAmbientSoundOn ? (
                  <div className="flex items-end gap-[2px] h-[18px] w-[18px]">
                    <span className="w-[3px] bg-[#d4a853] soundwave-bar inline-block rounded-full"></span>
                    <span className="w-[3px] bg-[#d4a853] soundwave-bar inline-block rounded-full"></span>
                    <span className="w-[3px] bg-[#d4a853] soundwave-bar inline-block rounded-full"></span>
                    <span className="w-[3px] bg-[#d4a853] soundwave-bar inline-block rounded-full"></span>
                  </div>
                ) : (
                  <VolumeX className="w-[18px] h-[18px]" />
                )}
              </button>

              <button 
                onClick={() => { setIsReservationOpen(true); playSoundEffect('click'); }}
                className="font-sans-inter text-[11px] tracking-[0.15em] uppercase bg-gradient-to-r from-[#d4a853] via-[#e5bd68] to-[#bda043] text-[#0c0b0a] font-bold px-7 py-3 rounded-full shadow-[0_4px_20px_rgba(212,168,83,0.35)] border border-[#ffea9f]/40 transition-all duration-300 hover:scale-105 hover:brightness-110"
                onMouseEnter={() => { setCursorHovering(true); playSoundEffect('hover'); }}
                onMouseLeave={() => setCursorHovering(false)}
              >
                Secure Seating &rarr;
              </button>
            </div>

            {/* Mobile Navigation Toggle */}
            <button 
              onClick={() => setMobileMenuOpen(!mobileMenuOpen)}
              className="md:hidden bg-[#1c1813] border border-[#d4a853]/50 p-2.5 rounded-full text-[#d4a853] hover:text-white"
              aria-label="Toggle menu"
            >
              {mobileMenuOpen ? (
                <svg className="w-5 h-5" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                  <path strokeLinecap="round" strokeLinejoin="round" strokeWidth={1.5} d="M6 18L18 6M6 6l12 12" />
                </svg>
              ) : (
                <svg className="w-5 h-5" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                  <path strokeLinecap="round" strokeLinejoin="round" strokeWidth={1.5} d="M4 6h16M4 12h16M4 18h16" />
                </svg>
              )}
            </button>
          </div>

          {/* Mobile Overlay Menu */}
          <div className={`md:hidden absolute top-28 left-0 w-full bg-[#1c1813] border-b border-[#d4a853]/40 shadow-2xl transition-all duration-300 ease-in-out origin-top ${mobileMenuOpen ? 'opacity-100 scale-y-100' : 'opacity-0 scale-y-0 pointer-events-none'}`}>
            <div className="px-6 py-8 flex flex-col space-y-4 font-sans-inter text-xs tracking-[0.2em] uppercase">
              <button onClick={() => scrollToSection('menu')} className="text-left text-[#f4f3f0] py-2 border-b border-[#2d2926]">The Alchemy</button>
              <button onClick={() => scrollToSection('forge')} className="text-left text-[#f4f3f0] py-2 border-b border-[#2d2926]">Alchemical Lab</button>
              <button onClick={() => scrollToSection('vault')} className="text-left text-[#f4f3f0] py-2 border-b border-[#2d2926]">3D Vault</button>
              <button onClick={() => scrollToSection('cellar')} className="text-left text-[#f4f3f0] py-2 border-b border-[#2d2926]">Obsidian Cellar</button>
              <button onClick={() => scrollToSection('tablemap')} className="text-left text-[#f4f3f0] py-2 border-b border-[#2d2926]">Communal Hearth Table</button>
              <button onClick={() => scrollToSection('chef')} className="text-left text-[#f4f3f0] py-2 border-b border-[#2d2926]">Chef Elina</button>
              <button 
                onClick={() => { setMobileMenuOpen(false); setIsReservationOpen(true); }} 
                className="w-full bg-[#d4a853] text-[#0c0b0a] font-bold py-3 text-center rounded-full mt-4 tracking-[0.15em] border border-[#ffea9f]/40"
              >
                Secure a Hearth Seat
              </button>
            </div>
          </div>
        </nav>
      </header>

      {/* Floating Atmosphere Controller HUD in the Bottom Right */}
      <div className="fixed bottom-8 left-8 z-[100] hidden lg:flex flex-col items-start gap-2 bg-[#121110]/95 border border-[#d4a853]/40 p-4 rounded-2xl shadow-[0_10px_35px_rgba(212,168,83,0.3)] backdrop-blur-md">
        <span className="font-sans-inter text-[9px] tracking-[0.2em] uppercase text-[#d4a853] font-bold">VALO Atmosphere Controller</span>
        <div className="flex items-center space-x-2 mt-1">
          <button 
            onClick={() => { setGlobalTheme('fire'); playSoundEffect('click'); }}
            className={`px-3 py-1.5 rounded-full text-[9px] tracking-wider uppercase font-sans-inter font-bold transition-all border ${
              globalTheme === 'fire' 
                ? 'bg-[#d4a853] text-[#0c0b0a] border-[#d4a853]' 
                : 'bg-[#1c1813] text-[#a8a19a] border-[#d4a853]/20 hover:border-[#d4a853]'
            }`}
          >
            Solar Fire
          </button>
          <button 
            onClick={() => { setGlobalTheme('frost'); playSoundEffect('click'); }}
            className={`px-3 py-1.5 rounded-full text-[9px] tracking-wider uppercase font-sans-inter font-bold transition-all border ${
              globalTheme === 'frost' 
                ? 'bg-blue-500 text-[#0c0b0a] border-blue-400' 
                : 'bg-[#1c1813] text-[#a8a19a] border-[#d4a853]/20 hover:border-blue-400'
            }`}
          >
            Glacial Frost
          </button>
        </div>
      </div>

      {/* Audio Ambient Simulator Player Element */}
      {isAmbientSoundOn && (
        <iframe 
          src="https://www.youtube.com/embed/L_LUpnjgPso?autoplay=1&mute=0&loop=1&playlist=L_LUpnjgPso" 
          className="hidden" 
          title="Ambient hearth fireplace soundtrack"
        />
      )}

      {}
      <section 
        id="hero" 
        className="relative min-h-screen flex items-end justify-start pt-32 pb-16 lg:pb-24 overflow-hidden bg-[#0c0b0a]"
        style={{
          opacity: isScrolling ? 0.8 : 1.0,
          filter: isScrolling ? 'blur(1px)' : 'blur(0px)',
          transition: 'opacity 0.8s cubic-bezier(0.16, 1, 0.3, 1), filter 0.8s cubic-bezier(0.16, 1, 0.3, 1)'
        }}
      >
        {/* Dynamic vertical 3D image slices - Highly Visible and Seeable */}
        <div className="absolute inset-0 z-0 flex pointer-events-none select-none">
          {/* Vertical slice 1 */}
          <div 
            className="w-1/3 h-full overflow-hidden border-r border-[#d4a853]/35 relative transition-transform duration-[150ms] ease-out"
            style={{
              transform: `perspective(1200px) translateY(${smoothScrollY * -0.16}px) rotateY(${mousePos.x * 12}deg) translateZ(${smoothScrollY * 0.04}px) scale(1.15)`,
            }}
          >
            <img 
              src="https://images.unsplash.com/photo-1544025162-d76694265947?auto=format&fit=crop&q=80&w=1920" 
              alt="Hearth Kitchen"
              className="absolute left-0 top-0 h-full w-[300vw] max-w-none object-cover opacity-75 filter sepia-[0.1] brightness-[0.85] contrast-[1.1]"
              style={{
                transform: `translateX(${smoothScrollY * 0.05}px) scale(1.15)`,
                transition: 'transform 0.1s ease-out'
              }}
            />
          </div>

          {/* Vertical slice 2 */}
          <div 
            className="w-1/3 h-full overflow-hidden border-r border-[#d4a853]/35 relative transition-transform duration-[150ms] ease-out"
            style={{
              transform: `perspective(1200px) translateY(${smoothScrollY * 0.1}px) rotateY(${mousePos.x * -8}deg) translateZ(${smoothScrollY * -0.05}px) scale(1.2)`,
            }}
          >
            <img 
              src="https://images.unsplash.com/photo-1544025162-d76694265947?auto=format&fit=crop&q=80&w=1920" 
              alt="Roaring Hearth"
              className="absolute left-[-100%] top-0 h-full w-[300vw] max-w-none object-cover opacity-85 filter sepia-[0.1] brightness-[0.8] contrast-[1.15]"
              style={{
                transform: `translateX(${smoothScrollY * -0.03}px) scale(1.2)`,
                transition: 'transform 0.1s ease-out'
              }}
            />
          </div>

          {/* Vertical slice 3 */}
          <div 
            className="w-1/3 h-full overflow-hidden relative transition-transform duration-[150ms] ease-out"
            style={{
              transform: `perspective(1200px) translateY(${smoothScrollY * -0.12}px) rotateY(${mousePos.x * 16}deg) translateZ(${smoothScrollY * 0.08}px) scale(1.15)`,
            }}
          >
            <img 
              src="https://images.unsplash.com/photo-1544025162-d76694265947?auto=format&fit=crop&q=80&w=1920" 
              alt="Nordic Fireplace"
              className="absolute left-[-200%] top-0 h-full w-[300vw] max-w-none object-cover opacity-75 filter sepia-[0.1] brightness-[0.85] contrast-[1.1]"
              style={{
                transform: `translateX(${smoothScrollY * 0.04}px) scale(1.15)`,
                transition: 'transform 0.1s ease-out'
              }}
            />
          </div>

          {/* Golden Ambient Lighting Overlays (Optimized to keep background extremely seeable) */}
          <div 
            className="absolute inset-0"
            style={{
              background: 'linear-gradient(to top, rgba(12,11,10,0.95) 0%, rgba(12,11,10,0.5) 45%, rgba(12,11,10,0.1) 100%)'
            }}
          />
          <div className="absolute inset-0 bg-radial-at-c from-transparent via-[#0c0b0a]/15 to-[#0c0b0a]/70"></div>
          <div className="absolute top-1/4 left-1/4 w-[600px] h-[600px] bg-[#d4a853]/15 rounded-full filter blur-[150px] mix-blend-color-dodge"></div>
        </div>

        {/* Hero Interactive Contents with 3D Float Matrix */}
        <div className="relative z-20 max-w-7xl mx-auto px-6 lg:px-12 w-full">
          <div 
            className="max-w-4xl text-left flex flex-col items-start transition-transform duration-[200ms] ease-out bg-[#0c0b0a]/80 backdrop-blur-md p-8 lg:p-12 rounded-3xl border border-[#d4a853]/30 shadow-2xl"
            style={{
              transform: `perspective(1000px) rotateX(${mousePos.y * -4}deg) rotateY(${mousePos.x * 4}deg) translateY(${smoothScrollY * -0.12}px)`
            }}
          >
            
            <div className="inline-flex items-center space-x-2 bg-[#1c1813] border border-[#d4a853] px-5 py-2.5 rounded-full mb-6 backdrop-blur-md relative overflow-hidden group shadow-[0_4px_15px_rgba(212,168,83,0.25)]">
              <span className="w-2 h-2 bg-[#d4a853] rounded-full animate-ping"></span>
              <span className="font-serif-cormorant italic text-xs lg:text-sm text-[#d4a853] tracking-widest relative z-10 font-bold">
                Established 2020 · Mayfair, London
              </span>
              <div className="absolute inset-0 bg-gradient-to-r from-transparent via-[#d4a853]/20 to-transparent translate-x-[-100%] group-hover:translate-x-[100%] transition-transform duration-1000" />
            </div>

            <h1 className="font-serif-cormorant font-semibold text-white tracking-tight leading-[1.05] mb-6 drop-shadow-3xl select-none"
                style={{ fontSize: 'clamp(44px, 8.5vw, 110px)' }}>
              A Culinary <br />
              <span className="text-[#d4a853] italic">Symphony</span> <br />
              Of Foraged Fire
            </h1>

            <p className="font-sans-inter font-light text-base lg:text-lg text-[#f4f3f0]/95 max-w-xl mb-8 leading-relaxed">
              An immersive exploration of modern Nordic gastronomy, born from wild woodlands, deep ice horizons, and open hearth flames.
            </p>

            <div className="flex flex-col sm:flex-row items-stretch sm:items-center space-y-4 sm:space-y-0 sm:space-x-5 w-full sm:w-auto">
              <button 
                onClick={() => { setIsReservationOpen(true); playSoundEffect('click'); }}
                className="font-sans-inter text-xs tracking-[0.2em] uppercase bg-gradient-to-r from-[#d4a853] to-[#bda043] hover:from-[#e5bd68] hover:to-[#d4a853] text-[#0c0b0a] font-bold px-9 py-4 rounded-full transition-all duration-300 flex items-center justify-center space-x-2 shadow-lg shadow-[#d4a853]/30 border border-[#ffea9f]/40 group relative overflow-hidden"
                onMouseEnter={() => { setCursorHovering(true); playSoundEffect('hover'); }}
                onMouseLeave={() => setCursorHovering(false)}
              >
                <span className="relative z-10">Enter the Threshold</span>
                <span className="absolute inset-0 bg-gradient-to-r from-white/0 via-white/20 to-white/0 translate-x-[-100%] group-hover:translate-x-[100%] transition-transform duration-700 ease-out"></span>
              </button>
              <button 
                onClick={() => scrollToSection('menu')}
                className="font-sans-inter text-xs tracking-[0.2em] uppercase border border-[#d4a853] text-[#d4a853] bg-[#1c1813]/60 hover:bg-[#d4a853]/10 px-9 py-4 rounded-full transition-all duration-300 flex items-center justify-center space-x-2 relative group shadow-[0_4px_15px_rgba(212,168,83,0.15)]"
                onMouseEnter={() => { setCursorHovering(true); playSoundEffect('hover'); }}
                onMouseLeave={() => setCursorHovering(false)}
              >
                <span className="group-hover:translate-x-1 transition-transform duration-300">Explore the Alchemy &rarr;</span>
              </button>
            </div>
          </div>
        </div>

        <div className="absolute bottom-8 right-12 hidden lg:flex items-center space-x-4 text-xs font-sans-inter tracking-[0.15em] text-[#d4a853] z-20 font-bold bg-[#0c0b0a]/80 px-4 py-2 rounded-full border border-[#d4a853]/30 backdrop-blur-sm">
          <span className="w-12 h-px bg-[#d4a853]"></span>
          <span>Unveil the elemental cycles</span>
        </div>
      </section>

      {}
      <section 
        id="philosophy"
        className="relative py-32 bg-[#121110] border-y border-[#d4a853]/30 overflow-hidden min-h-[45vh] flex items-center"
      >
        {/* Full-bleed 3D background wrapper - High Contrast & Visibility */}
        <div 
          className="absolute inset-0 z-0 pointer-events-none select-none transition-transform duration-[150ms] ease-out scale-110"
          style={{
            transform: `perspective(1000px) translateY(${(smoothScrollY - 600) * 0.12}px) rotateY(${mousePos.x * 5}deg) translateZ(-50px)`
          }}
        >
          <img 
            src="https://images.unsplash.com/photo-1482862549707-f63cb32c5fd9?auto=format&fit=crop&q=80&w=1920" 
            alt="Dark Nordic Winter" 
            className="absolute inset-0 w-full h-full object-cover opacity-65 filter contrast-125 sepia-[0.2] brightness-[0.75]"
          />
          <div className="absolute inset-0 bg-gradient-to-b from-[#0c0b0a]/90 via-[#0c0b0a]/30 to-[#0c0b0a]/90" />
        </div>

        <div className="absolute inset-0 bg-gradient-to-r from-transparent via-[#d4a853]/10 to-transparent pointer-events-none z-10"></div>
        
        <div className="max-w-7xl mx-auto px-6 lg:px-12 flex flex-col md:flex-row items-center justify-center text-center relative z-20 w-full">
          
          <div className="bg-[#0c0b0a]/85 backdrop-blur-md p-10 lg:p-14 rounded-3xl border border-[#d4a853]/25 shadow-2xl flex flex-col md:flex-row items-center justify-center max-w-5xl">
            <div 
              className="hidden md:block h-0.5 bg-gradient-to-r from-transparent to-[#d4a853] origin-right transition-transform duration-[1200ms] ease-out"
              style={{ 
                width: '100px', 
                transform: `scaleX(${smoothScrollProgress > 0.04 ? 1 : 0})`,
                marginRight: '2.5rem'
              }}
            />

            <p className="font-serif-cormorant italic text-xl lg:text-3xl text-[#f4f3f0] px-4 max-w-3xl leading-relaxed text-shadow-glow">
              "Nature is not a pantry to be plundered, but a sacred cathedral where we listen to the silent whisper of the <span className="text-[#d4a853] font-bold">frost</span> and the roaring scream of the <span className="text-[#d4a853] font-bold">flame</span>."
            </p>

            <div 
              className="hidden md:block h-0.5 bg-gradient-to-l from-transparent to-[#d4a853] origin-left transition-transform duration-[1200ms] ease-out"
              style={{ 
                width: '100px', 
                transform: `scaleX(${smoothScrollProgress > 0.04 ? 1 : 0})`,
                marginLeft: '2.5rem'
              }}
            />
          </div>
        </div>
      </section>

      {}
      <section 
        id="menu" 
        className="py-24 lg:py-32 bg-[#0c0b0a] relative overflow-hidden"
        style={{
          opacity: isScrolling ? 0.8 : 1.0,
          transition: 'opacity 0.6s ease-out'
        }}
      >
        {/* Full-bleed 3D background wrapper - Elevated to 50% opacity for sharp visibility */}
        <div 
          className="absolute inset-0 z-0 pointer-events-none select-none transition-transform duration-[150ms] ease-out scale-110"
          style={{
            transform: `perspective(1000px) translateY(${(smoothScrollY - 1200) * -0.1}px) rotateY(${mousePos.x * -6}deg) translateZ(-40px)`
          }}
        >
          <img 
            src="https://images.unsplash.com/photo-1555396273-367ea4eb4db5?auto=format&fit=crop&q=80&w=1920" 
            alt="Culinary closeups" 
            className="absolute inset-0 w-full h-full object-cover opacity-50 filter brightness-[0.7] contrast-125 saturate-[0.8]"
          />
          <div className="absolute inset-0 bg-gradient-to-b from-[#121110]/95 via-transparent to-[#121110]/95" />
        </div>

        <div className="absolute top-1/2 left-1/2 w-[800px] h-[800px] -translate-x-1/2 -translate-y-1/2 bg-[#d4a853]/5 rounded-full filter blur-[180px] pointer-events-none z-0"></div>

        <div className="max-w-7xl mx-auto px-6 lg:px-12 relative z-20">
          
          <div className="text-center mb-16 reveal-on-scroll">
            <span className="font-sans-inter text-xs tracking-[0.25em] uppercase text-[#d4a853] block mb-2 font-bold bg-[#0c0b0a]/80 px-4 py-1.5 rounded-full border border-[#d4a853]/20 inline-block">Seasonal Elemental Acts</span>
            <h2 className="font-serif-cormorant text-4xl lg:text-5xl font-semibold text-white inline-block relative pb-4 mt-3">
              The Alchemy
              <span className="absolute bottom-0 left-1/4 right-1/4 h-0.5 bg-gradient-to-r from-transparent via-[#d4a853] to-transparent" />
            </h2>
          </div>

          {/* Interactive Menu Tabs */}
          <div className="flex justify-center space-x-2 md:space-x-4 mb-16 max-w-lg mx-auto border-b border-[#d4a853]/20 pb-4 reveal-on-scroll bg-[#0c0b0a]/75 backdrop-blur-md p-2 rounded-full">
            {[
              { id: 'firstSeeding', label: 'First Seeding' },
              { id: 'elementalFire', label: 'Elemental Fire' },
              { id: 'deepFreeze', label: 'Deep Freeze' }
            ].map((tab) => (
              <button
                key={tab.id}
                onClick={() => { setActiveMenuTab(tab.id); playSoundEffect('click'); }}
                className={`flex-1 font-sans-inter text-[11px] tracking-[0.15em] uppercase py-2.5 rounded-full border transition-all duration-300 text-center ${
                  activeMenuTab === tab.id 
                    ? 'bg-[#d4a853] border-[#d4a853] text-[#0c0b0a] font-bold shadow-[0_4px_15px_rgba(212,168,83,0.35)]' 
                    : 'bg-[#1c1813] border-[#d4a853]/30 text-[#a8a19a] hover:text-[#f4f3f0] hover:border-[#d4a853]'
                }`}
                onMouseEnter={() => { setCursorHovering(true); playSoundEffect('hover'); }}
                onMouseLeave={() => setCursorHovering(false)}
              >
                {tab.label}
              </button>
            ))}
          </div>

          {/* Sliced Dynamic Grid of Items with luxurious glass backing container */}
          <div className="grid grid-cols-1 lg:grid-cols-12 gap-12 items-center">
            
            {/* Left Column: Menu list items with glass panel background */}
            <div className="lg:col-span-6 transition-all duration-500 ease-in-out bg-[#0c0b0a]/80 backdrop-blur-md p-6 lg:p-10 rounded-3xl border border-[#d4a853]/25 shadow-2xl">
              {activeMenuTab === 'firstSeeding' && (
                <div className="space-y-4">
                  <div className="group border-b border-[#d4a853]/20 py-5 transition-all duration-300 hover:bg-[#1c1813]/40 hover:px-6 premium-glow-border reveal-on-scroll">
                    <div className="flex justify-between items-baseline mb-1">
                      <h3 className="font-serif-cormorant text-xl lg:text-2xl font-medium text-[#f4f3f0] group-hover:text-[#d4a853] transition-colors duration-300">Birch Consommé</h3>
                      <span className="font-sans-inter text-sm text-[#d4a853] font-bold">&pound;19</span>
                    </div>
                    <p className="font-sans-inter text-xs lg:text-sm text-[#a8a19a] font-light leading-relaxed">
                      Fermented spring birch sap, wild mountain sorrel oil, and hand-gathered woodland lichen cracknel.
                    </p>
                  </div>
                  <div className="group border-b border-[#d4a853]/20 py-5 transition-all duration-300 hover:bg-[#1c1813]/40 hover:px-6 premium-glow-border reveal-on-scroll">
                    <div className="flex justify-between items-baseline mb-1">
                      <h3 className="font-serif-cormorant text-xl lg:text-2xl font-medium text-[#f4f3f0] group-hover:text-[#d4a853] transition-colors duration-300">Juniper Venison Tartare</h3>
                      <span className="font-sans-inter text-sm text-[#d4a853] font-bold">&pound;22</span>
                    </div>
                    <p className="font-sans-inter text-xs lg:text-sm text-[#a8a19a] font-light leading-relaxed">
                      Cold-cured Cairngorms venison, salted cloudberries, wild pine needle oil, and dynamic rye crisps.
                    </p>
                  </div>
                  <div className="group border-b border-[#d4a853]/20 py-5 transition-all duration-300 hover:bg-[#1c1813]/40 hover:px-6 premium-glow-border reveal-on-scroll">
                    <div className="flex justify-between items-baseline mb-1">
                      <h3 className="font-serif-cormorant text-xl lg:text-2xl font-medium text-[#f4f3f0] group-hover:text-[#d4a853] transition-colors duration-300">Ash-Roasted Carrots</h3>
                      <span className="font-sans-inter text-sm text-[#d4a853] font-bold">&pound;17</span>
                    </div>
                    <p className="font-sans-inter text-xs lg:text-sm text-[#a8a19a] font-light leading-relaxed">
                      Embers-charred heritage root vegetables, elderberry reduction, whipped goat curd, and sea buckthorn dust.
                    </p>
                  </div>
                  <div className="group border-b border-[#d4a853]/20 py-5 transition-all duration-300 hover:bg-[#1c1813]/40 hover:px-6 premium-glow-border reveal-on-scroll">
                    <div className="flex justify-between items-baseline mb-1">
                      <h3 className="font-serif-cormorant text-xl lg:text-2xl font-medium text-[#f4f3f0] group-hover:text-[#d4a853] transition-colors duration-300">Shetland Diver Scallops</h3>
                      <span className="font-sans-inter text-sm text-[#d4a853] font-bold">&pound;25</span>
                    </div>
                    <p className="font-sans-inter text-xs lg:text-sm text-[#a8a19a] font-light leading-relaxed">
                      Pan-kissed giants, fermented parsnip emulsion, fire-rendered wild boar fat, and crispy coastal samphire.
                    </p>
                  </div>
                </div>
              )}

              {activeMenuTab === 'elementalFire' && (
                <div className="space-y-4">
                  <div className="group border-b border-[#d4a853]/20 py-5 transition-all duration-300 hover:bg-[#1c1813]/40 hover:px-6 premium-glow-border reveal-on-scroll">
                    <div className="flex justify-between items-baseline mb-1">
                      <h3 className="font-serif-cormorant text-xl lg:text-2xl font-medium text-[#f4f3f0] group-hover:text-[#d4a853] transition-colors duration-300">Hay-Smoked Cod</h3>
                      <span className="font-sans-inter text-sm text-[#d4a853] font-bold">&pound;36</span>
                    </div>
                    <p className="font-sans-inter text-xs lg:text-sm text-[#a8a19a] font-light leading-relaxed">
                      Line-caught Atlantic cod loin, charred leek velvet, beach herb dashi, and home-fermented kelp butter.
                    </p>
                  </div>
                  <div className="group border-b border-[#d4a853]/20 py-5 transition-all duration-300 hover:bg-[#1c1813]/40 hover:px-6 premium-glow-border reveal-on-scroll">
                    <div className="flex justify-between items-baseline mb-1">
                      <h3 className="font-serif-cormorant text-xl lg:text-2xl font-medium text-[#f4f3f0] group-hover:text-[#d4a853] transition-colors duration-300">Charcoal Forest Boar</h3>
                      <span className="font-sans-inter text-sm text-[#d4a853] font-bold">&pound;39</span>
                    </div>
                    <p className="font-sans-inter text-xs lg:text-sm text-[#a8a19a] font-light leading-relaxed">
                      Open-flame roasted wild boar rack, sweet rowanberry gel, woodruff root broth, and salt-baked wild roots.
                    </p>
                  </div>
                  <div className="group border-b border-[#d4a853]/20 py-5 transition-all duration-300 hover:bg-[#1c1813]/40 hover:px-6 premium-glow-border reveal-on-scroll">
                    <div className="flex justify-between items-baseline mb-1">
                      <h3 className="font-serif-cormorant text-xl lg:text-2xl font-medium text-[#f4f3f0] group-hover:text-[#d4a853] transition-colors duration-300">Highland Elk Medallion</h3>
                      <span className="font-sans-inter text-sm text-[#d4a853] font-bold">&pound;49</span>
                    </div>
                    <p className="font-sans-inter text-xs lg:text-sm text-[#a8a19a] font-light leading-relaxed">
                      Spruce bark-wrapped tenderloin, fermented black garlic paste, roasted forest chanterelles, and warm heather jus.
                    </p>
                  </div>
                  <div className="group border-b border-[#d4a853]/20 py-5 transition-all duration-300 hover:bg-[#1c1813]/40 hover:px-6 premium-glow-border reveal-on-scroll">
                    <div className="flex justify-between items-baseline mb-1">
                      <h3 className="font-serif-cormorant text-xl lg:text-2xl font-medium text-[#f4f3f0] group-hover:text-[#d4a853] transition-colors duration-300">Roasted Rye Dumplings</h3>
                      <span className="font-sans-inter text-sm text-[#d4a853] font-bold">&pound;31</span>
                    </div>
                    <p className="font-sans-inter text-xs lg:text-sm text-[#a8a19a] font-light leading-relaxed">
                      Hand-rolled smoked rye pastry filled with autumn wild mushrooms, charred allium cream, and local pine pollen.
                    </p>
                  </div>
                </div>
              )}

              {activeMenuTab === 'deepFreeze' && (
                <div className="space-y-4">
                  <div className="group border-b border-[#d4a853]/20 py-5 transition-all duration-300 hover:bg-[#1c1813]/40 hover:px-6 premium-glow-border reveal-on-scroll">
                    <div className="flex justify-between items-baseline mb-1">
                      <h3 className="font-serif-cormorant text-xl lg:text-2xl font-medium text-[#f4f3f0] group-hover:text-[#d4a853] transition-colors duration-300">Pine Needle Parfait</h3>
                      <span className="font-sans-inter text-sm text-[#d4a853] font-bold">&pound;14</span>
                    </div>
                    <p className="font-sans-inter text-xs lg:text-sm text-[#a8a19a] font-light leading-relaxed">
                      Frost-crystallized Scots pine needles, dark birch syrup glaze, and wild mountain berry sorbet.
                    </p>
                  </div>
                  <div className="group border-b border-[#d4a853]/20 py-5 transition-all duration-300 hover:bg-[#1c1813]/40 hover:px-6 premium-glow-border reveal-on-scroll">
                    <div className="flex justify-between items-baseline mb-1">
                      <h3 className="font-serif-cormorant text-xl lg:text-2xl font-medium text-[#f4f3f0] group-hover:text-[#d4a853] transition-colors duration-300">Wood Woodruff Mille-Feuille</h3>
                      <span className="font-sans-inter text-sm text-[#d4a853] font-bold">&pound;16</span>
                    </div>
                    <p className="font-sans-inter text-xs lg:text-sm text-[#a8a19a] font-light leading-relaxed">
                      Crisp structural pastry leaves, wild cloudberry curd, sweet woodruff-steeped cream, and golden honey crunch.
                    </p>
                  </div>
                  <div className="group border-b border-[#d4a853]/20 py-5 transition-all duration-300 hover:bg-[#1c1813]/40 hover:px-6 premium-glow-border reveal-on-scroll">
                    <div className="flex justify-between items-baseline mb-1">
                      <h3 className="font-serif-cormorant text-xl lg:text-2xl font-medium text-[#f4f3f0] group-hover:text-[#d4a853] transition-colors duration-300">Nordic Artisan Curations</h3>
                      <span className="font-sans-inter text-sm text-[#d4a853] font-bold">&pound;20</span>
                    </div>
                    <p className="font-sans-inter text-xs lg:text-sm text-[#a8a19a] font-light leading-relaxed">
                      A collection of cave-aged northern cheeses, wild rosehip jelly, dense walnut-honey bread, and dry barley crackers.
                    </p>
                  </div>
                  <div className="group border-b border-[#d4a853]/20 py-5 transition-all duration-300 hover:bg-[#1c1813]/40 hover:px-6 premium-glow-border reveal-on-scroll">
                    <div className="flex justify-between items-baseline mb-1">
                      <h3 className="font-serif-cormorant text-xl lg:text-2xl font-medium text-[#f4f3f0] group-hover:text-[#d4a853] transition-colors duration-300">Scorched Birch Bark Tart</h3>
                      <span className="font-sans-inter text-sm text-[#d4a853] font-bold">&pound;15</span>
                    </div>
                    <p className="font-sans-inter text-xs lg:text-sm text-[#a8a19a] font-light leading-relaxed">
                      Caramelized wood sugars, toasted buckwheat base, dark alder-smoked sea salt crystals, and wild blackberry juice.
                    </p>
                  </div>
                </div>
              )}
            </div>

            {/* Right Column: Dynamic Overhauled 3D Image Collage segment */}
            <div className="lg:col-span-6 h-[500px] relative reveal-on-scroll flex items-center justify-center">
              
              {/* Backing Particle Visualizer Canvas focused inside frame */}
              <div className="absolute inset-0 z-0 bg-[#121110]/70 border border-[#d4a853]/30 rounded-3xl overflow-hidden shadow-[inset_0_0_40px_rgba(212,168,83,0.15)]">
                <canvas 
                  ref={alchemyCanvasRef} 
                  className="w-full h-full block opacity-95 transition-all duration-500"
                />
              </div>

              {/* OVERLAPPING 3D COLLAGE: Image 1 - Enhanced Contrast and Brightness */}
              <div 
                id="alchemy-img-1"
                onMouseMove={(e) => handleTiltMove(e, 'alc1')}
                onMouseLeave={() => handleTiltLeave('alc1')}
                className="absolute w-[200px] h-[280px] rounded-2xl overflow-hidden shadow-2xl z-10 left-[8%] top-[10%] parallax-frame-container transition-transform duration-[150ms] ease-out border border-[#d4a853]/40"
                style={{
                  transform: `perspective(1000px) rotateX(${tiltState.alc1?.x || 0}deg) rotateY(${tiltState.alc1?.y || 0}deg) translateY(${smoothScrollY * -0.06}px) scale(0.95)`,
                  '--shine-x': `${tiltState.alc1?.shineX || 50}%`,
                  '--shine-y': `${tiltState.alc1?.shineY || 50}%`
                }}
              >
                <div className="hologram-shine"></div>
                <img 
                  src="https://images.unsplash.com/photo-1513836279014-a89f7a76ae86?auto=format&fit=crop&q=80&w=600" 
                  alt="Pine Forest" 
                  className="w-full h-full object-cover filter contrast-[1.2] sepia-0 brightness-95"
                  style={{ transform: `scale(1.25) translateY(${smoothScrollY * 0.04}px)` }}
                />
              </div>

              {/* OVERLAPPING 3D COLLAGE: Image 2 - Highly Visible */}
              <div 
                id="alchemy-img-2"
                onMouseMove={(e) => handleTiltMove(e, 'alc2')}
                onMouseLeave={() => handleTiltLeave('alc2')}
                className="absolute w-[220px] h-[220px] rounded-full border-2 border-[#d4a853] overflow-hidden shadow-[0_15px_35px_rgba(212,168,83,0.35)] z-20 right-[10%] top-[20%] parallax-frame-container transition-transform duration-[120ms] ease-out"
                style={{
                  transform: `perspective(1000px) rotateX(${tiltState.alc2?.x || 0}deg) rotateY(${tiltState.alc2?.y || 0}deg) translateY(${smoothScrollY * 0.08}px) scale(1.15)`,
                  '--shine-x': `${tiltState.alc2?.shineX || 50}%`,
                  '--shine-y': `${tiltState.alc2?.shineY || 50}%`
                }}
              >
                <div className="hologram-shine"></div>
                <img 
                  src="https://images.unsplash.com/photo-1546069901-ba9599a7e63c?auto=format&fit=crop&q=80&w=600" 
                  alt="Nordic Plated Alchemy" 
                  className="w-full h-full object-cover filter brightness-[0.9] contrast-[1.1]"
                  style={{ transform: `scale(1.2) translateY(${smoothScrollY * -0.06}px)` }}
                />
              </div>

              {/* OVERLAPPING 3D COLLAGE: Image 3 */}
              <div 
                id="alchemy-img-3"
                onMouseMove={(e) => handleTiltMove(e, 'alc3')}
                onMouseLeave={() => handleTiltLeave('alc3')}
                className="absolute w-[140px] h-[180px] rounded-xl overflow-hidden shadow-2xl z-30 left-[35%] bottom-[8%] parallax-frame-container transition-transform duration-[100ms] ease-out border border-[#d4a853]/40"
                style={{
                  transform: `perspective(1000px) rotateX(${tiltState.alc3?.x || 0}deg) rotateY(${tiltState.alc3?.y || 0}deg) translateY(${smoothScrollY * -0.14}px) scale(1.05)`,
                  '--shine-x': `${tiltState.alc3?.shineX || 50}%`,
                  '--shine-y': `${tiltState.alc3?.shineY || 50}%`
                }}
              >
                <div className="hologram-shine"></div>
                <img 
                  src="https://images.unsplash.com/photo-1615485290382-441e4d049cb5?auto=format&fit=crop&q=80&w=600" 
                  alt="Foraged Berries" 
                  className="w-full h-full object-cover filter brightness-[0.95] saturate-[1.15] contrast-[1.1]"
                  style={{ transform: `scale(1.3) translateY(${smoothScrollY * 0.08}px)` }}
                />
              </div>

              {/* Shimmering Gold Crucible Accent HUD */}
              <div className="absolute top-4 left-4 font-sans-inter text-[9px] tracking-[0.3em] uppercase text-[#d4a853] font-bold z-10 bg-[#0c0b0a]/95 border border-[#d4a853]/40 px-3.5 py-1.5 rounded-full shadow-[0_4px_12px_rgba(212,168,83,0.2)]">
                <span>Crucible Active: {activeMenuTab === 'firstSeeding' ? 'Spring Sap' : activeMenuTab === 'elementalFire' ? 'Live Fire' : 'Glacial Ice'}</span>
              </div>

            </div>

          </div>

          <div className="text-center mt-16 reveal-on-scroll">
            <button 
              onClick={() => { setIsReservationOpen(true); playSoundEffect('click'); }}
              className="font-sans-inter text-xs tracking-[0.2em] uppercase border border-[#d4a853] text-[#d4a853] hover:bg-[#d4a853] hover:text-[#0c0b0a] font-bold px-9 py-4 rounded-full transition-all duration-300 inline-block bg-[#1c1813] shadow-[0_4px_15px_rgba(212,168,83,0.15)]"
              onMouseEnter={() => { setCursorHovering(true); playSoundEffect('hover'); }}
              onMouseLeave={() => setCursorHovering(false)}
            >
              Reserve an Alchemy Seat &rarr;
            </button>
          </div>

        </div>
      </section>

      {}
      <section 
        id="forge" 
        className="py-24 lg:py-32 bg-[#121110] border-y border-[#d4a853]/20 relative overflow-hidden"
      >
        {/* Full-bleed 3D background wrapper - High opacity/contrast, completely seeable */}
        <div 
          className="absolute inset-0 z-0 pointer-events-none select-none transition-transform duration-[150ms] ease-out scale-110"
          style={{
            transform: `perspective(1000px) translateY(${(smoothScrollY - 2000) * 0.1}px) rotateY(${mousePos.x * 4}deg) translateZ(-45px)`
          }}
        >
          <img 
            src="https://images.unsplash.com/photo-1516594709413-7135457b4436?auto=format&fit=crop&q=80&w=1920" 
            alt="Laboratory bottles" 
            className="absolute inset-0 w-full h-full object-cover opacity-50 filter brightness-[0.55] contrast-125 saturate-[0.9]"
          />
          <div className="absolute inset-0 bg-gradient-to-b from-[#0c0b0a]/90 via-[#0c0b0a]/30 to-[#0c0b0a]/90" />
        </div>

        <div className="absolute inset-0 pointer-events-none bg-radial-at-c from-[#d4a853]/10 to-transparent"></div>
        <div className="max-w-7xl mx-auto px-6 lg:px-12 relative z-20">
          
          <div className="text-center mb-16 reveal-on-scroll">
            <span className="font-sans-inter text-xs tracking-[0.25em] uppercase text-[#d4a853] block mb-2 font-bold bg-[#0c0b0a]/80 px-4 py-1.5 rounded-full border border-[#d4a853]/20 inline-block">The Interactive Kitchen Lab</span>
            <h2 className="font-serif-cormorant text-4xl lg:text-5xl font-semibold text-white inline-block relative pb-4 mt-3">
              Forager's Alchemical Forge
              <span className="absolute bottom-0 left-1/4 right-1/4 h-0.5 bg-gradient-to-r from-transparent via-[#d4a853] to-transparent" />
            </h2>
          </div>

          <div className="grid grid-cols-1 lg:grid-cols-12 gap-12 items-center">
            
            {/* Left Box: Ingredient Selection Grid with elegant card glass backing */}
            <div className="lg:col-span-6 space-y-6 reveal-on-scroll bg-[#0c0b0a]/80 backdrop-blur-md p-8 lg:p-12 rounded-3xl border border-[#d4a853]/25 shadow-2xl">
              <h3 className="font-serif-cormorant text-2xl lg:text-3xl font-medium text-white">Select Nordic Elements</h3>
              <p className="font-sans-inter text-xs lg:text-sm text-[#a8a19a] leading-relaxed font-light">
                Combine up to three wild native botanicals inside our hearth crucible to simulate the physical and chemical cooking preparations developed by Chef Elina.
              </p>

              <div className="grid grid-cols-1 sm:grid-cols-2 gap-4 pt-4">
                {rawIngredients.map((ing) => {
                  const isSelected = forgeInventory.includes(ing.id);
                  return (
                    <button
                      key={ing.id}
                      onClick={() => handleIngredientToggle(ing.id)}
                      className={`p-4 rounded-xl text-left border transition-all duration-300 relative overflow-hidden group ${
                        isSelected 
                          ? 'bg-[#1c1813] border-[#d4a853] shadow-[0_0_15px_rgba(212,168,83,0.15)]' 
                          : 'bg-[#0c0b0a] border-[#d4a853]/20 hover:border-[#d4a853]/50'
                      }`}
                    >
                      <div className="flex justify-between items-center mb-2">
                        <span className={`font-serif-cormorant text-lg font-bold ${isSelected ? 'text-[#d4a853]' : 'text-white'}`}>{ing.label}</span>
                        {isSelected && <span className="w-2.5 h-2.5 bg-[#d4a853] rounded-full animate-pulse" />}
                      </div>
                      <p className="font-sans-inter text-[11px] text-[#a8a19a] font-light leading-normal">{ing.desc}</p>
                    </button>
                  );
                })}
              </div>

              <div className="pt-4">
                <button
                  onClick={executeAlchemyForge}
                  className="px-8 py-3.5 bg-gradient-to-r from-[#d4a853] to-[#bda043] text-[#0c0b0a] font-sans-inter text-xs tracking-widest font-bold uppercase rounded-full shadow-lg hover:brightness-110 transition-all w-full sm:w-auto"
                >
                  Merge Elements & Forge Recipe
                </button>
              </div>
            </div>

            {/* Right Box: Output Display Panel */}
            <div className="lg:col-span-6 reveal-on-scroll flex items-center justify-center">
              <div className="w-full max-w-md bg-[#0c0b0a]/90 backdrop-blur-md border-2 border-[#d4a853]/60 rounded-3xl p-8 relative overflow-hidden shadow-2xl">
                <div className="absolute top-0 left-0 right-0 h-[1px] bg-gradient-to-r from-transparent via-[#d4a853] to-transparent" />
                <div className="absolute -bottom-16 -right-16 w-32 h-32 bg-[#d4a853]/15 rounded-full filter blur-xl" />

                <div className="text-center space-y-4">
                  <div className="w-16 h-16 bg-[#1c1813] border border-[#d4a853] rounded-full flex items-center justify-center mx-auto text-[#d4a853]">
                    <Sparkles className="w-6 h-6 animate-spin" />
                  </div>
                  
                  <span className="font-sans-inter text-[9px] tracking-[0.2em] uppercase text-[#d4a853] font-bold block">Crucible Chambers</span>
                  
                  {forgeOutcome ? (
                    <div className="space-y-4 animate-fade-in">
                      <h4 className="font-serif-cormorant text-2xl font-bold text-white italic">{forgeOutcome.title}</h4>
                      <p className="font-sans-inter text-xs text-[#a8a19a] leading-relaxed max-w-xs mx-auto font-light">
                        {forgeOutcome.desc}
                      </p>
                      <div className="pt-2">
                        <span className="inline-block bg-[#1c1813] border border-[#d4a853]/40 text-[#d4a853] text-[9px] uppercase tracking-widest px-4 py-1.5 rounded-full">
                          Ready for Curing
                        </span>
                      </div>
                    </div>
                  ) : (
                    <div className="space-y-3">
                      <h4 className="font-serif-cormorant text-xl text-[#a8a19a]">The Forge is Cold</h4>
                      <p className="font-sans-inter text-xs text-[#a8a19a]/70 font-light leading-relaxed max-w-xs mx-auto">
                        No recipe forged yet. Tap up to three botanical raw elements from the laboratory list to ignite the flames.
                      </p>
                      {forgeInventory.length > 0 && (
                        <div className="flex justify-center gap-2 pt-2">
                          {forgeInventory.map(id => (
                            <span key={id} className="text-[10px] bg-[#1c1813] text-[#d4a853] px-3 py-1 rounded-full border border-[#d4a853]/30">
                              {rawIngredients.find(i => i.id === id)?.label}
                            </span>
                          ))}
                        </div>
                      )}
                    </div>
                  )}

                </div>
              </div>
            </div>

          </div>

        </div>
      </section>

      {}
      <section 
        id="vault"
        className="py-24 lg:py-32 bg-[#0c0b0a] border-t border-[#d4a853]/20 relative overflow-hidden"
      >
        {/* Full-bleed 3D background wrapper - High opacity, completely seeable */}
        <div 
          className="absolute inset-0 z-0 pointer-events-none select-none transition-transform duration-[150ms] ease-out scale-110"
          style={{
            transform: `perspective(1000px) translateY(${(smoothScrollY - 2800) * -0.1}px) rotateY(${mousePos.x * -5}deg) translateZ(-50px)`
          }}
        >
          <img 
            src="https://images.unsplash.com/photo-1464822759023-fed622ff2c3b?auto=format&fit=crop&q=80&w=1920" 
            alt="Mountain Cavern Background" 
            className="absolute inset-0 w-full h-full object-cover opacity-50 filter brightness-[0.55] contrast-125 sepia-[0.1]"
          />
          <div className="absolute inset-0 bg-gradient-to-b from-[#121110]/95 via-transparent to-[#121110]/95" />
        </div>

        <div className="max-w-7xl mx-auto px-6 lg:px-12 relative z-20">
          
          <div className="text-center mb-12 reveal-on-scroll">
            <span className="font-sans-inter text-xs tracking-[0.25em] uppercase text-[#d4a853] block mb-2 font-bold bg-[#0c0b0a]/80 px-4 py-1.5 rounded-full border border-[#d4a853]/20 inline-block">Tactical Chamber Metrics & Holographics</span>
            <h2 className="font-serif-cormorant text-4xl lg:text-5xl font-semibold text-white inline-block relative pb-4 mt-3">
              Vault of Fire & Ice
              <span className="absolute bottom-0 left-1/4 right-1/4 h-0.5 bg-gradient-to-r from-transparent via-[#d4a853] to-transparent" />
            </h2>
          </div>

          {/* Interactive Vault 3D Selection Deck */}
          <div className="grid grid-cols-1 lg:grid-cols-12 gap-8 items-stretch mb-12 reveal-on-scroll">
            
            {/* Hearth Selector */}
            <div 
              onClick={() => { setSelectedVaultChamber('hearth'); playSoundEffect('click'); }}
              className={`lg:col-span-4 p-6 rounded-2xl border transition-all duration-500 cursor-pointer flex flex-col justify-between relative overflow-hidden group ${
                selectedVaultChamber === 'hearth'
                  ? 'bg-[#1c1813] border-[#d4a853] shadow-[0_0_30px_rgba(212,168,83,0.25)]'
                  : 'bg-[#121110]/80 border-[#d4a853]/20 hover:border-[#d4a853]/50'
              }`}
            >
              <div className="flex items-center justify-between mb-4">
                <span className="font-sans-inter text-[10px] uppercase tracking-wider text-[#a8a19a]">Chamber alpha</span>
                <Flame className={`w-5 h-5 ${selectedVaultChamber === 'hearth' ? 'text-[#d4a853]' : 'text-[#a8a19a]'}`} />
              </div>
              <div>
                <h3 className="font-serif-cormorant text-2xl font-bold text-white mb-2">Thermodynamic Hearth</h3>
                <p className="font-sans-inter text-xs text-[#a8a19a] leading-relaxed font-light">
                  Active live wood fire pit operating at 400°C for intense caramelizations and instant searing.
                </p>
              </div>
              <div className="mt-4 pt-4 border-t border-[#d4a853]/10 flex items-center justify-between text-[11px] font-sans-inter">
                <span className="text-[#d4a853] font-bold">420°C Limit</span>
                <span className="text-[#a8a19a]">Active fuel: Pine</span>
              </div>
            </div>

            {/* Cryo Stone Selector */}
            <div 
              onClick={() => { setSelectedVaultChamber('scallop'); playSoundEffect('click'); }}
              className={`lg:col-span-4 p-6 rounded-2xl border transition-all duration-500 cursor-pointer flex flex-col justify-between relative overflow-hidden group ${
                selectedVaultChamber === 'scallop'
                  ? 'bg-[#1c1813] border-[#d4a853] shadow-[0_0_30px_rgba(212,168,83,0.25)]'
                  : 'bg-[#121110]/80 border-[#d4a853]/20 hover:border-[#d4a853]/50'
              }`}
            >
              <div className="flex items-center justify-between mb-4">
                <span className="font-sans-inter text-[10px] uppercase tracking-wider text-[#a8a19a]">Chamber beta</span>
                <Wind className={`w-5 h-5 ${selectedVaultChamber === 'scallop' ? 'text-[#d4a853]' : 'text-[#a8a19a]'}`} />
              </div>
              <div>
                <h3 className="font-serif-cormorant text-2xl font-bold text-white mb-2">Glacial Stone Casing</h3>
                <p className="font-sans-inter text-xs text-[#a8a19a] leading-relaxed font-light">
                  Hollowed volcanic stones conditioned at cryogenic levels to lock in seafood aromatics instantly.
                </p>
              </div>
              <div className="mt-4 pt-4 border-t border-[#d4a853]/10 flex items-center justify-between text-[11px] font-sans-inter">
                <span className="text-blue-400 font-bold">4°C Steady</span>
                <span className="text-[#a8a19a]">Cooling Basalt</span>
              </div>
            </div>

            {/* Chimney Selector */}
            <div 
              onClick={() => { setSelectedVaultChamber('chimney'); playSoundEffect('click'); }}
              className={`lg:col-span-4 p-6 rounded-2xl border transition-all duration-500 cursor-pointer flex flex-col justify-between relative overflow-hidden group ${
                selectedVaultChamber === 'chimney'
                  ? 'bg-[#1c1813] border-[#d4a853] shadow-[0_0_30px_rgba(212,168,83,0.25)]'
                  : 'bg-[#121110]/80 border-[#d4a853]/20 hover:border-[#d4a853]/50'
              }`}
            >
              <div className="flex items-center justify-between mb-4">
                <span className="font-sans-inter text-[10px] uppercase tracking-wider text-[#a8a19a]">Chamber gamma</span>
                <Sliders className={`w-5 h-5 ${selectedVaultChamber === 'chimney' ? 'text-[#d4a853]' : 'text-[#a8a19a]'}`} />
              </div>
              <div>
                <h3 className="font-serif-cormorant text-2xl font-bold text-white mb-2">Charcoal Aging Cell</h3>
                <p className="font-sans-inter text-xs text-[#a8a19a] leading-relaxed font-light">
                  Continuous low-velocity draft chimneys pulling cold forest wood smoke across protein fibers.
                </p>
              </div>
              <div className="mt-4 pt-4 border-t border-[#d4a853]/10 flex items-center justify-between text-[11px] font-sans-inter">
                <span className="text-[#d4a853] font-bold">110°C Smoking</span>
                <span className="text-[#a8a19a]">Alder Shards</span>
              </div>
            </div>

          </div>

          {}
          {/* Main Vault Tactical Specifications and Holographic simulation panels */}
          <div className="grid grid-cols-1 lg:grid-cols-12 gap-12 items-stretch reveal-on-scroll">
            
            {/* Left Blueprint Spec Console */}
            <div className="lg:col-span-6 bg-[#0c0b0a]/90 backdrop-blur-md border border-[#d4a853]/45 rounded-3xl p-8 shadow-2xl relative flex flex-col justify-between overflow-hidden">
              <div className="absolute top-0 left-0 right-0 h-[1.5px] bg-gradient-to-r from-transparent via-[#d4a853] to-transparent" />
              
              <div className="space-y-6">
                <div className="flex justify-between items-center">
                  <div>
                    <span className="font-sans-inter text-[9px] tracking-widest text-[#d4a853] uppercase font-bold block">
                      {vaultChambersData[selectedVaultChamber].subtitle}
                    </span>
                    <h3 className="font-serif-cormorant text-3xl font-bold text-white mt-1">
                      {vaultChambersData[selectedVaultChamber].title}
                    </h3>
                  </div>
                  <div className="px-3.5 py-1.5 rounded-full bg-[#1c1813] border border-[#d4a853]/40 text-[#d4a853] text-[10px] font-sans-inter font-bold uppercase animate-pulse">
                    Live telemetry
                  </div>
                </div>

                <p className="font-sans-inter text-xs lg:text-sm text-[#a8a19a] leading-relaxed font-light">
                  {vaultChambersData[selectedVaultChamber].technicalNotes}
                </p>

                {/* Tactical Parameters Indicators Grid */}
                <div className="grid grid-cols-2 gap-4 bg-[#121110] border border-[#d4a853]/20 rounded-2xl p-4 text-xs font-sans-inter">
                  <div className="space-y-1">
                    <span className="text-[#a8a19a] block text-[10px] uppercase">Temperature level</span>
                    <span className="text-white font-bold block">{vaultChambersData[selectedVaultChamber].temp}</span>
                  </div>
                  <div className="space-y-1">
                    <span className="text-[#a8a19a] block text-[10px] uppercase">Atmosphere humidity</span>
                    <span className="text-white font-bold block">{vaultChambersData[selectedVaultChamber].humidity}</span>
                  </div>
                  <div className="space-y-1 col-span-2 border-t border-[#d4a853]/15 pt-2">
                    <span className="text-[#a8a19a] block text-[10px] uppercase">Active fuel composition</span>
                    <span className="text-[#d4a853] font-bold block">{vaultChambersData[selectedVaultChamber].fuel}</span>
                  </div>
                </div>
              </div>

              {/* Chef Kannel field notebook excerpt block */}
              <div className="mt-8 pt-6 border-t border-[#d4a853]/20 space-y-2">
                <span className="font-serif-cormorant text-xs italic text-[#d4a853] font-bold block">
                  Field Notebook Excerpt · Chef Elina Kannel
                </span>
                <p className="font-sans-inter text-xs text-[#a8a19a] leading-normal italic font-light">
                  "{vaultChambersData[selectedVaultChamber].chefRecommendation}"
                </p>
              </div>

            </div>

            {/* Right Blueprint Vector/Particle simulation frame */}
            <div className="lg:col-span-6 bg-[#121110]/95 border border-[#d4a853]/40 rounded-3xl p-8 relative flex flex-col justify-between overflow-hidden min-h-[420px] shadow-2xl">
              
              {/* Backing Thermal Curves canvas */}
              <div className="absolute inset-0 z-0 opacity-80 pointer-events-none">
                <canvas 
                  ref={vaultCanvasRef} 
                  className="w-full h-full block"
                />
              </div>

              {/* Schematic vs Sensory Profiles Tab triggers */}
              <div className="relative z-10 flex space-x-2 border-b border-[#d4a853]/20 pb-4 mb-4">
                <button
                  onClick={() => { setViewedChamberMetric('schematic'); playSoundEffect('click'); }}
                  className={`px-4 py-2 rounded-full font-sans-inter text-[10px] tracking-wider uppercase border transition-all ${
                    viewedChamberMetric === 'schematic'
                      ? 'bg-[#d4a853] text-[#0c0b0a] border-[#d4a853] font-bold'
                      : 'bg-[#1c1813] text-[#a8a19a] border-transparent hover:border-[#d4a853]/50'
                  }`}
                >
                  Thermal schematic
                </button>
                <button
                  onClick={() => { setViewedChamberMetric('profile'); playSoundEffect('click'); }}
                  className={`px-4 py-2 rounded-full font-sans-inter text-[10px] tracking-wider uppercase border transition-all ${
                    viewedChamberMetric === 'profile'
                      ? 'bg-[#d4a853] text-[#0c0b0a] border-[#d4a853] font-bold'
                      : 'bg-[#1c1813] text-[#a8a19a] border-transparent hover:border-[#d4a853]/50'
                  }`}
                >
                  Flavour Sensory Radar
                </button>
              </div>

              {/* View Output Area */}
              <div className="relative z-10 flex-1 flex flex-col justify-center">
                {viewedChamberMetric === 'schematic' ? (
                  /* Elegant Vector SVG Blueprint schematic layout */
                  <div className="space-y-6 text-center">
                    <svg className="w-48 h-48 mx-auto text-[#d4a853]/60" viewBox="0 0 200 200" fill="none">
                      <circle cx="100" cy="100" r="80" stroke="currentColor" strokeWidth="1" strokeDasharray="4 4" />
                      <circle cx="100" cy="100" r="50" stroke="currentColor" strokeWidth="1.5" />
                      <circle cx="100" cy="100" r="20" stroke="currentColor" strokeWidth="1" />
                      <line x1="20" y1="100" x2="180" y2="100" stroke="currentColor" strokeWidth="0.5" />
                      <line x1="100" y1="20" x2="100" y2="180" stroke="currentColor" strokeWidth="0.5" />
                      
                      {/* Interactive technical text specs labels inside SVG */}
                      <text x="110" y="45" fill="currentColor" fontSize="7" className="font-sans-inter">Ventilation vector: active</text>
                      <text x="110" y="165" fill="currentColor" fontSize="7" className="font-sans-inter">Combustion angle: 32deg</text>
                    </svg>
                    <span className="font-sans-inter text-[9px] uppercase text-[#a8a19a] tracking-widest block">
                      Mayfair Bruton Outpost · Chamber Blueprint {selectedVaultChamber.toUpperCase()}-099
                    </span>
                  </div>
                ) : (
                  /* Dynamic sensory charts layout with progress bars */
                  <div className="space-y-4 max-w-sm mx-auto w-full">
                    <span className="font-sans-inter text-[9px] uppercase tracking-wider text-[#a8a19a] block text-center mb-2">
                      Organoleptic Taste Distribution profile
                    </span>
                    
                    {/* Umami Bar */}
                    <div className="space-y-1">
                      <div className="flex justify-between text-xs font-sans-inter text-[#a8a19a]">
                        <span>Umami intensity</span>
                        <span className="text-white font-bold">{vaultChambersData[selectedVaultChamber].profile.umami}%</span>
                      </div>
                      <div className="h-1.5 w-full bg-[#1c1813] rounded-full overflow-hidden border border-[#d4a853]/20">
                        <div 
                          className="h-full bg-[#d4a853] rounded-full transition-all duration-1000"
                          style={{ width: `${vaultChambersData[selectedVaultChamber].profile.umami}%` }}
                        />
                      </div>
                    </div>

                    {/* Acidic Bar */}
                    <div className="space-y-1">
                      <div className="flex justify-between text-xs font-sans-inter text-[#a8a19a]">
                        <span>Acidic contrast</span>
                        <span className="text-white font-bold">{vaultChambersData[selectedVaultChamber].profile.acidic}%</span>
                      </div>
                      <div className="h-1.5 w-full bg-[#1c1813] rounded-full overflow-hidden border border-[#d4a853]/20">
                        <div 
                          className="h-full bg-[#d4a853] rounded-full transition-all duration-1000"
                          style={{ width: `${vaultChambersData[selectedVaultChamber].profile.acidic}%` }}
                        />
                      </div>
                    </div>

                    {/* Bitter Bar */}
                    <div className="space-y-1">
                      <div className="flex justify-between text-xs font-sans-inter text-[#a8a19a]">
                        <span>Woodland Bitter elements</span>
                        <span className="text-white font-bold">{vaultChambersData[selectedVaultChamber].profile.bitter}%</span>
                      </div>
                      <div className="h-1.5 w-full bg-[#1c1813] rounded-full overflow-hidden border border-[#d4a853]/20">
                        <div 
                          className="h-full bg-[#d4a853] rounded-full transition-all duration-1000"
                          style={{ width: `${vaultChambersData[selectedVaultChamber].profile.bitter}%` }}
                        />
                      </div>
                    </div>

                    {/* Aromatic Bar */}
                    <div className="space-y-1">
                      <div className="flex justify-between text-xs font-sans-inter text-[#a8a19a]">
                        <span>Evergreen Aromatics depth</span>
                        <span className="text-white font-bold">{vaultChambersData[selectedVaultChamber].profile.aromatic}%</span>
                      </div>
                      <div className="h-1.5 w-full bg-[#1c1813] rounded-full overflow-hidden border border-[#d4a853]/20">
                        <div 
                          className="h-full bg-[#d4a853] rounded-full transition-all duration-1000"
                          style={{ width: `${vaultChambersData[selectedVaultChamber].profile.aromatic}%` }}
                        />
                      </div>
                    </div>

                  </div>
                )}
              </div>

              <div className="relative z-10 text-center text-[10px] font-sans-inter text-[#a8a19a] pt-4 border-t border-[#d4a853]/15 mt-4">
                Selected: {vaultChambersData[selectedVaultChamber].title} Telemetry Feed
              </div>

            </div>

          </div>

        </div>
      </section>

      {}
      <section 
        id="cellar"
        className="py-24 lg:py-32 bg-[#121110] border-y border-[#d4a853]/20 relative overflow-hidden"
      >
        {/* Full-bleed 3D background wrapper - Elevating opacity to make casks visible */}
        <div 
          className="absolute inset-0 z-0 pointer-events-none select-none transition-transform duration-[150ms] ease-out scale-110"
          style={{
            transform: `perspective(1000px) translateY(${(smoothScrollY - 3600) * 0.12}px) rotateY(${mousePos.x * 6}deg) translateZ(-40px)`
          }}
        >
          <img 
            src="https://images.unsplash.com/photo-1560624052-449f5ddf0c31?auto=format&fit=crop&q=80&w=1920" 
            alt="Wine Cellar Stone Background" 
            className="absolute inset-0 w-full h-full object-cover opacity-55 filter brightness-[0.5] contrast-125 saturate-[0.8] sepia-[0.2]"
          />
          <div className="absolute inset-0 bg-gradient-to-b from-[#0c0b0a]/90 via-[#0c0b0a]/35 to-[#0c0b0a]/90" />
        </div>

        <div className="absolute inset-0 pointer-events-none bg-radial-at-t from-[#d4a853]/10 to-transparent"></div>
        <div className="max-w-7xl mx-auto px-6 lg:px-12 relative z-20">
          
          <div className="grid grid-cols-1 lg:grid-cols-12 gap-12 items-center">
            
            <div className="lg:col-span-5 space-y-6 reveal-on-scroll bg-[#0c0b0a]/80 backdrop-blur-md p-8 lg:p-12 rounded-3xl border border-[#d4a853]/25 shadow-2xl">
              <div className="inline-flex items-center space-x-2 bg-[#1c1813] border border-[#d4a853] px-4 py-2 rounded-full">
                <Wine className="w-4 h-4 text-[#d4a853]" />
                <span className="font-sans-inter text-[10px] tracking-[0.2em] uppercase text-[#d4a853] font-bold">The Obsidian Cellar</span>
              </div>
              
              <h2 className="font-serif-cormorant text-4xl lg:text-5xl font-bold text-white leading-tight">
                Deep Underground <br />
                <span className="text-[#d4a853] italic">Subterranean Aging</span>
              </h2>
              
              <p className="font-sans-inter font-light text-sm lg:text-base text-[#a8a19a] leading-relaxed">
                Hidden six meters below Bruton Place lies our temperature-shielded vault. Here, rare glacial meads, biodynamic vintages, and mountain forest distillates undergo complex chemical maturations.
              </p>

              {/* Subterranean Vintage Reserve Timeline selector */}
              <div className="border border-[#d4a853]/30 p-6 rounded-2xl bg-[#0c0b0a]">
                <span className="font-sans-inter text-[9px] tracking-[0.2em] uppercase text-[#d4a853] font-bold block mb-3">Vintage Exploration timeline</span>
                
                <div className="flex space-x-2 border-b border-[#d4a853]/20 pb-3 mb-4">
                  {Object.keys(vintageReserves).map((year) => (
                    <button
                      key={year}
                      onClick={() => { setSelectedVintageYear(year); playSoundEffect('click'); }}
                      className={`px-3.5 py-1.5 rounded-lg text-xs font-sans-inter font-bold transition-all ${
                        selectedVintageYear === year 
                          ? 'bg-[#d4a853] text-[#0c0b0a] font-bold' 
                          : 'bg-[#1c1813] text-[#a8a19a] hover:text-white'
                      }`}
                    >
                      {year}
                    </button>
                  ))}
                </div>

                <div className="space-y-1.5 animate-fade-in">
                  <span className="font-serif-cormorant text-lg text-white font-bold block">
                    {vintageReserves[selectedVintageYear].name}
                  </span>
                  <span className="font-sans-inter text-[10px] text-[#d4a853] uppercase tracking-wider block">
                    Origin: {vintageReserves[selectedVintageYear].region}
                  </span>
                  <p className="font-sans-inter text-xs text-[#a8a19a] font-light mt-2 leading-relaxed">
                    {vintageReserves[selectedVintageYear].notes}
                  </p>
                  <span className="inline-block text-[9px] text-[#ffea9f]/65 bg-[#d4a853]/15 border border-[#d4a853]/30 px-3 py-1 rounded-full mt-3">
                    {vintageReserves[selectedVintageYear].stock}
                  </span>
                </div>
              </div>
            </div>

            <div className="lg:col-span-7 h-[480px] relative reveal-on-scroll flex items-center justify-center">
              
              {/* Overlaid Parallax Cellar Casks Frame */}
              <div 
                onMouseMove={(e) => handleTiltMove(e, 'c1')}
                onMouseLeave={() => handleTiltLeave('c1')}
                className="absolute w-[280px] h-[380px] rounded-2xl overflow-hidden shadow-2xl transition-transform duration-300 ease-out z-10 left-[5%] parallax-frame-container border border-[#d4a853]/30"
                style={{
                  transform: `perspective(1000px) rotateX(${tiltState.c1?.x || 0}deg) rotateY(${tiltState.c1?.y || 0}deg) translateY(${smoothScrollY * -0.05}px)`,
                  '--shine-x': `${tiltState.c1?.shineX || 50}%`,
                  '--shine-y': `${tiltState.c1?.shineY || 50}%`
                }}
              >
                <div className="hologram-shine"></div>
                <img 
                  src="https://images.unsplash.com/photo-1510812431401-41d2bd2722f3?auto=format&fit=crop&q=80&w=600" 
                  alt="Wine Casks" 
                  className="w-full h-full object-cover filter brightness-[0.8] sepia-[0.1]"
                  style={{ transform: `scale(1.2) translateY(${smoothScrollY * 0.03}px)` }}
                />
              </div>

              {/* Overlaid Parallax Mead Bottle Frame */}
              <div 
                onMouseMove={(e) => handleTiltMove(e, 'c2')}
                onMouseLeave={() => handleTiltLeave('c2')}
                className="absolute w-[240px] h-[340px] border border-[#d4a853] rounded-2xl overflow-hidden shadow-[0_10px_35px_rgba(212,168,83,0.25)] transition-transform duration-[150ms] ease-out z-20 right-[5%] bottom-[5%] parallax-frame-container"
                style={{
                  transform: `perspective(1000px) rotateX(${tiltState.c2?.x || 0}deg) rotateY(${tiltState.c2?.y || 0}deg) translateY(${smoothScrollY * -0.15}px) scale(1.05)`,
                  '--shine-x': `${tiltState.c2?.shineX || 50}%`,
                  '--shine-y': `${tiltState.c2?.shineY || 50}%`
                }}
              >
                <div className="hologram-shine"></div>
                <img 
                  src="https://images.unsplash.com/photo-1514362545857-3bc16c4c7d1b?auto=format&fit=crop&q=80&w=600" 
                  alt="Glacial Mead decanting" 
                  className="w-full h-full object-cover filter brightness-[0.85] contrast-110"
                  style={{ transform: `scale(1.35) translateY(${smoothScrollY * -0.05}px)` }}
                />
              </div>

            </div>

          </div>

        </div>
      </section>

      {}
      <section 
        id="tablemap" 
        className="py-24 lg:py-32 bg-[#0c0b0a] border-b border-[#d4a853]/20 relative overflow-hidden"
      >
        {/* Full-bleed 3D background wrapper - Opacity elevated to 45% for high visibility */}
        <div 
          className="absolute inset-0 z-0 pointer-events-none select-none transition-transform duration-[150ms] ease-out scale-110"
          style={{
            transform: `perspective(1000px) translateY(${(smoothScrollY - 4400) * -0.1}px) rotateY(${mousePos.x * -4}deg) translateZ(-45px)`
          }}
        >
          <img 
            src="https://images.unsplash.com/photo-1414235077428-338989a2e8c0?auto=format&fit=crop&q=80&w=1920" 
            alt="Table Setup Macro Background" 
            className="absolute inset-0 w-full h-full object-cover opacity-45 filter brightness-[0.55] contrast-[1.1] saturate-[0.8]"
          />
          <div className="absolute inset-0 bg-gradient-to-b from-[#121110]/95 via-transparent to-[#121110]/95" />
        </div>

        <div className="absolute top-0 right-0 w-[450px] h-[450px] bg-[#d4a853]/5 rounded-full filter blur-[130px] pointer-events-none" />
        <div className="max-w-7xl mx-auto px-6 lg:px-12 relative z-20">
          
          <div className="text-center mb-16 reveal-on-scroll">
            <span className="font-sans-inter text-xs tracking-[0.25em] uppercase text-[#d4a853] block mb-2 font-bold bg-[#0c0b0a]/80 px-4 py-1.5 rounded-full border border-[#d4a853]/20 inline-block">Choose Your Fire Perspective</span>
            <h2 className="font-serif-cormorant text-4xl lg:text-5xl font-semibold text-white inline-block relative pb-4 mt-3">
              Hearth Seating Blueprint
              <span className="absolute bottom-0 left-1/4 right-1/4 h-0.5 bg-gradient-to-r from-transparent via-[#d4a853] to-transparent" />
            </h2>
          </div>

          <div className="grid grid-cols-1 lg:grid-cols-12 gap-12 items-center">
            
            {/* Left Segment: SVG Interactive Table Map with solid background to pop out */}
            <div className="lg:col-span-7 flex justify-center reveal-on-scroll">
              <div className="relative w-full max-w-[440px] aspect-square bg-[#121110]/90 border border-[#d4a853]/40 rounded-full p-8 shadow-2xl flex items-center justify-center">
                <svg className="w-full h-full" viewBox="0 0 400 400">
                  <defs>
                    <radialGradient id="tableGlow" cx="50%" cy="50%" r="50%">
                      <stop offset="0%" stopColor="#d4a853" stopOpacity="0.3" />
                      <stop offset="100%" stopColor="#121110" stopOpacity="0" />
                    </radialGradient>
                  </defs>

                  <circle cx="200" cy="200" r="160" fill="url(#tableGlow)" />
                  <circle cx="200" cy="200" r="110" fill="#1c1813" stroke="#d4a853" strokeWidth="2" />
                  <circle cx="200" cy="200" r="45" fill="#0c0b0a" stroke="#d4a853" strokeWidth="1" strokeDasharray="6 4" />
                  <path d="M190,215 C190,185 200,170 200,170 C200,170 210,185 210,215 C210,225 201,230 200,230 C199,230 190,225 190,215 Z" fill="#d4a853" opacity="0.8" className="animate-pulse" />

                  {/* 12 Interactive Seats coordinates */}
                  {[...Array(12)].map((_, index) => {
                    const angle = (index * 30 * Math.PI) / 180;
                    const r = 140; 
                    const cx = 200 + r * Math.cos(angle);
                    const cy = 200 + r * Math.sin(angle);
                    const isSelected = selectedSeat === index;

                    return (
                      <g 
                        key={index} 
                        className="cursor-pointer group"
                        onClick={() => { setSelectedSeat(index % seatsData.length); playSoundEffect('click'); }}
                      >
                        <line x1="200" y1="200" x2={cx} y2={cy} stroke="#d4a853" strokeWidth="0.5" strokeDasharray="3 3" opacity="0.3" />
                        <circle 
                          cx={cx} 
                          cy={cy} 
                          r={isSelected ? 16 : 12} 
                          fill={isSelected ? '#d4a853' : '#121110'} 
                          stroke="#d4a853" 
                          strokeWidth="1.5" 
                          className="transition-all duration-300 group-hover:scale-110"
                        />
                        <text 
                          x={cx} 
                          y={cy + 4} 
                          fill={isSelected ? '#0c0b0a' : '#d4a853'} 
                          fontSize="10" 
                          fontWeight="bold" 
                          textAnchor="middle"
                          className="font-sans-inter"
                        >
                          {index + 1}
                        </text>
                      </g>
                    );
                  })}
                </svg>

                <div className="absolute font-sans-inter text-[9px] text-[#a8a19a] tracking-[0.2em] uppercase text-center pointer-events-none">
                  <span className="text-[#d4a853] font-bold block">Central Fire Pit</span>
                  <span>400°C</span>
                </div>
              </div>
            </div>

            {/* Right Segment: Seating vantage point description */}
            <div className="lg:col-span-5 space-y-6 reveal-on-scroll">
              <span className="font-sans-inter text-[10px] tracking-[0.25em] uppercase text-[#d4a853] font-bold block bg-[#0c0b0a]/80 px-4 py-1 inline-block rounded-full border border-[#d4a853]/20">Selected Coordinate Details</span>
              
              <div className="bg-[#121110]/95 backdrop-blur-md border border-[#d4a853] p-8 rounded-3xl space-y-4 shadow-2xl relative overflow-hidden">
                <div className="absolute top-0 left-0 w-1.5 h-full bg-[#d4a853]" />

                <span className="text-[#d4a853] font-serif-cormorant text-xs italic block font-bold">
                  {seatsData[selectedSeat].pos}
                </span>
                
                <h3 className="font-serif-cormorant text-3xl font-semibold text-white leading-tight">
                  {seatsData[selectedSeat].name}
                </h3>
                
                <p className="font-sans-inter text-xs text-[#a8a19a] font-light leading-relaxed">
                  {seatsData[selectedSeat].desc}
                </p>

                <div className="pt-4 flex items-center gap-4 text-xs font-sans-inter">
                  <span className="text-[#d4a853] font-bold">✓ Direct Sommelier allocation</span>
                  <span className="text-[#d4a853] font-bold">✓ Hand-served courses</span>
                </div>
              </div>

              <div className="text-center sm:text-left">
                <button
                  onClick={() => { setIsReservationOpen(true); playSoundEffect('click'); }}
                  className="px-8 py-3.5 bg-[#121110] border border-[#d4a853] text-[#d4a853] hover:bg-[#d4a853] hover:text-[#0c0b0a] font-sans-inter text-xs font-bold uppercase tracking-widest rounded-full transition-all shadow-lg"
                >
                  Reserve This Specific View
                </button>
              </div>
            </div>

          </div>

        </div>
      </section>

      {}
      <section 
        id="chef" 
        className="py-24 lg:py-32 bg-[#0c0b0a] border-b border-[#d4a853]/20 relative overflow-hidden"
      >
        {/* Full-bleed 3D background wrapper - High opacity image of cooking space */}
        <div 
          className="absolute inset-0 z-0 pointer-events-none select-none transition-transform duration-[150ms] ease-out scale-110"
          style={{
            transform: `perspective(1000px) translateY(${(smoothScrollY - 5200) * 0.1}px) rotateY(${mousePos.x * 4}deg) translateZ(-40px)`
          }}
        >
          <img 
            src="https://images.unsplash.com/photo-1556910103-1c02745aae4d?auto=format&fit=crop&q=80&w=1920" 
            alt="Chef Cooking Background Layout" 
            className="absolute inset-0 w-full h-full object-cover opacity-50 filter brightness-[0.5] contrast-[1.2] sepia-[0.1]"
          />
          <div className="absolute inset-0 bg-gradient-to-b from-[#121110]/95 via-transparent to-[#121110]/95" />
        </div>

        <div className="absolute top-0 right-0 w-[500px] h-[500px] bg-[#d4a853]/5 rounded-full filter blur-[150px] pointer-events-none" />
        
        <div className="max-w-6xl mx-auto px-6 lg:px-12 relative z-20">
          <div className="grid grid-cols-1 lg:grid-cols-12 gap-12 lg:gap-20 items-center">
            
            {/* Split panel Chef portraits */}
            <div className="lg:col-span-5 h-[500px] relative group reveal-on-scroll flex items-center justify-center">
              
              {/* Background shift panel */}
              <div 
                onMouseMove={(e) => handleTiltMove(e, 'ch1')}
                onMouseLeave={() => handleTiltLeave('ch1')}
                className="absolute w-[220px] h-[340px] border border-[#d4a853]/30 overflow-hidden transform -translate-x-12 -translate-y-8 grayscale transition-all duration-700 group-hover:grayscale-0 group-hover:translate-x-[70px] parallax-frame-container"
                style={{
                  transform: `perspective(1000px) rotateX(${tiltState.ch1?.x || 0}deg) rotateY(${tiltState.ch1?.y || 0}deg)`,
                  '--shine-x': `${tiltState.ch1?.shineX || 50}%`,
                  '--shine-y': `${tiltState.ch1?.shineY || 50}%`
                }}
              >
                <div className="hologram-shine"></div>
                <img 
                  src="https://images.unsplash.com/photo-1581299894007-aaa50297cf16?auto=format&fit=crop&q=80&w=800" 
                  alt="Chef Elina details" 
                  className="w-full h-full object-cover"
                />
              </div>

              {/* Main foreground focus panel */}
              <div 
                onMouseMove={(e) => handleTiltMove(e, 'ch2')}
                onMouseLeave={() => handleTiltLeave('ch2')}
                className="absolute w-[250px] h-[370px] border-2 border-[#d4a853] overflow-hidden shadow-[0_15px_40px_rgba(212,168,83,0.3)] z-10 transition-transform duration-500 ease-out parallax-frame-container"
                style={{
                  transform: `perspective(1000px) rotateX(${(tiltState.ch2?.x || 0) * 1.2}deg) rotateY(${(tiltState.ch2?.y || 0) * 1.2}deg) scale(1.05)`,
                  '--shine-x': `${tiltState.ch2?.shineX || 50}%`,
                  '--shine-y': `${tiltState.ch2?.shineY || 50}%`
                }}
              >
                <div className="hologram-shine"></div>
                <img 
                  src="https://images.unsplash.com/photo-1581299894007-aaa50297cf16?auto=format&fit=crop&q=80&w=800" 
                  alt="Executive Pioneer Chef Elina Kannel of VALO" 
                  className="w-full h-full object-cover filter contrast-[1.05]"
                  style={{ transform: `scale(1.15) translateY(${mousePos.y * -10}px)` }}
                />
                <div className="absolute inset-0 bg-gradient-to-t from-[#0c0b0a]/95 via-transparent to-transparent opacity-80" />
              </div>

              {/* Float statement sticker */}
              <div 
                className="absolute w-[200px] h-[100px] bg-[#1c1813]/95 border border-[#d4a853] px-4 py-3 text-center backdrop-blur-md z-20 bottom-4 right-[-20px] shadow-2xl transform translate-x-4 translate-y-4"
                style={{
                  transform: `perspective(1000px) translateZ(30px) rotateY(${mousePos.x * 20}deg)`,
                }}
              >
                <span className="font-serif-cormorant italic text-xs lg:text-sm text-[#d4a853] tracking-wider block font-bold">"An uncompromised return to elemental origins"</span>
              </div>
            </div>

            <div className="lg:col-span-7 space-y-6 reveal-on-scroll bg-[#0c0b0a]/80 backdrop-blur-md p-8 lg:p-12 rounded-3xl border border-[#d4a853]/25 shadow-2xl">
              <div className="inline-block bg-[#1c1813] text-[#d4a853] text-[10px] tracking-[0.25em] font-sans-inter font-bold uppercase px-4 py-2 border border-[#d4a853] rounded-full shadow-[0_2px_10px_rgba(212,168,83,0.15)]">
                Culinary Alchemist
              </div>
              
              <h2 className="font-serif-cormorant text-4xl lg:text-5xl font-bold text-white tracking-tight">
                Chef Elina Kannel
              </h2>

              <div className="space-y-4 font-sans-inter text-sm lg:text-base font-light text-[#a8a19a] leading-relaxed">
                <p>
                  Elina spent over a decade deep in the arctic landscapes of Swedish Lapland and the outer Norwegian fjords, working alongside remote foraging collectives and boundary-pushing Michelin outposts before establishing VALO in 2020. Her path merges archaic hearth-cooking rituals with minimalistic presentation.
                </p>
                <p>
                  At VALO, her kitchen acts as an extension of the forest floor and pristine tides. Relying exclusively on wild-crafted British evergreens, ethically culled game, and coastal botanicals, every plate celebrates a profound respect for seasonal rhythms, preserved through ancient fermentations and live wood fire.
                </p>
              </div>

              <div className="pt-6 grid grid-cols-1 sm:grid-cols-3 gap-3">
                <div className="flex items-center space-x-3 bg-[#1c1813] border border-[#d4a853]/40 p-4 rounded-full hover:border-[#d4a853] transition-colors shadow-[0_4px_15px_rgba(212,168,83,0.1)]">
                  <div className="w-2.5 h-2.5 rounded-full bg-[#d4a853]" />
                  <span className="font-sans-inter text-[11px] font-bold tracking-wide text-white uppercase">Arctic Master</span>
                </div>
                <div className="flex items-center space-x-3 bg-[#1c1813] border border-[#d4a853]/40 p-4 rounded-full hover:border-[#d4a853] transition-colors shadow-[0_4px_15px_rgba(212,168,83,0.1)]">
                  <div className="w-2.5 h-2.5 rounded-full bg-[#d4a853]" />
                  <span className="font-sans-inter text-[11px] font-bold tracking-wide text-white uppercase">Wild Hearth Fire</span>
                </div>
                <div className="flex items-center space-x-3 bg-[#1c1813] border border-[#d4a853]/40 p-4 rounded-full hover:border-[#d4a853] transition-colors shadow-[0_4px_15px_rgba(212,168,83,0.1)]">
                  <div className="w-2.5 h-2.5 rounded-full bg-[#d4a853]" />
                  <span className="font-sans-inter text-[11px] font-bold tracking-wide text-white uppercase">Biodynamic Focus</span>
                </div>
              </div>
            </div>

          </div>
        </div>
      </section>

      {}
      <section 
        id="experiences" 
        className="py-24 lg:py-32 bg-[#0c0b0a] relative overflow-hidden"
      >
        {/* Full-bleed 3D background wrapper - High opacity table light backdrop */}
        <div 
          className="absolute inset-0 z-0 pointer-events-none select-none transition-transform duration-[150ms] ease-out scale-110"
          style={{
            transform: `perspective(1000px) translateY(${(smoothScrollY - 6000) * -0.1}px) rotateY(${mousePos.x * -5}deg) translateZ(-45px)`
          }}
        >
          <img 
            src="https://images.unsplash.com/photo-1533777857889-4be7c70b33f7?auto=format&fit=crop&q=80&w=1920" 
            alt="Outdoor Dining Lights Background" 
            className="absolute inset-0 w-full h-full object-cover opacity-50 filter brightness-[0.5] contrast-[1.2] saturate-[0.9]"
          />
          <div className="absolute inset-0 bg-gradient-to-b from-[#121110]/95 via-transparent to-[#121110]/95" />
        </div>

        <div className="max-w-6xl mx-auto px-6 lg:px-12 relative z-20">
          
          <div className="text-center mb-16 reveal-on-scroll">
            <span className="font-sans-inter text-xs tracking-[0.2em] uppercase text-[#d4a853] block mb-2 font-bold bg-[#0c0b0a]/80 px-4 py-1.5 rounded-full border border-[#d4a853]/20 inline-block">Sacred Gathering Acts</span>
            <h2 className="font-serif-cormorant text-4xl lg:text-5xl font-semibold text-white inline-block relative pb-4 mt-3">
              VALO Rituals
              <span className="absolute bottom-0 left-1/4 right-1/4 h-0.5 bg-gradient-to-r from-transparent via-[#d4a853] to-transparent" />
            </h2>
          </div>

          <div className="grid grid-cols-1 md:grid-cols-3 gap-8 mb-20">
            {/* Experience Card 1 */}
            <div 
              onMouseMove={(e) => handleTiltMove(e, 'exp1')}
              onMouseLeave={() => handleTiltLeave('exp1')}
              className="group bg-[#121110]/90 backdrop-blur-md border border-[#d4a853]/30 p-8 rounded-2xl transition-all duration-500 hover:border-[#d4a853] hover:shadow-[0_0_35px_rgba(212,168,83,0.25)] hover:-translate-y-1.5 flex flex-col justify-between reveal-on-scroll relative overflow-hidden"
              style={{
                transform: `perspective(1000px) rotateX(${tiltState.exp1?.x || 0}deg) rotateY(${tiltState.exp1?.y || 0}deg)`,
              }}
            >
              <div className="absolute inset-0 bg-gradient-to-tr from-[#d4a853]/5 to-transparent pointer-events-none opacity-0 group-hover:opacity-100 transition-opacity duration-500" />
              <div className="relative z-10">
                <div className="text-[#d4a853] mb-6 inline-block group-hover:scale-110 transition-transform duration-[350ms]">
                  <Flame className="w-8 h-8" />
                </div>
                <h3 className="font-serif-cormorant text-2xl font-semibold mb-4 text-white group-hover:text-[#d4a853] transition-colors duration-300">The Hearth Table</h3>
                <p className="font-sans-inter text-xs lg:text-sm text-[#a8a19a] leading-relaxed mb-6 font-light">
                  A private open-hearth sanctuary designed for intimate communal dinners of up to 12 guests. Fully curated fireside interaction led by Chef Elina.
                </p>
              </div>
              <button 
                onClick={() => { setIsReservationOpen(true); playSoundEffect('click'); setBookingData(prev => ({...prev, specialRequest: 'Hearth Table Inquiry'})); }}
                className="font-sans-inter text-[10px] tracking-[0.15em] uppercase text-[#d4a853] group-hover:text-white font-bold flex items-center space-x-2 transition-colors duration-300 pt-4 border-t border-[#d4a853]/20 relative z-10"
                onMouseEnter={() => { setCursorHovering(true); playSoundEffect('hover'); }}
                onMouseLeave={() => setCursorHovering(false)}
              >
                <span>Initiate &rarr;</span>
              </button>
            </div>

            {/* Experience Card 2 */}
            <div 
              onMouseMove={(e) => handleTiltMove(e, 'exp2')}
              onMouseLeave={() => handleTiltLeave('exp2')}
              className="group bg-[#121110]/90 backdrop-blur-md border border-[#d4a853]/30 p-8 rounded-2xl transition-all duration-500 hover:border-[#d4a853] hover:shadow-[0_0_35px_rgba(212,168,83,0.25)] hover:-translate-y-1.5 flex flex-col justify-between reveal-on-scroll relative overflow-hidden"
              style={{
                transform: `perspective(1000px) rotateX(${tiltState.exp2?.x || 0}deg) rotateY(${tiltState.exp2?.y || 0}deg)`,
              }}
            >
              <div className="absolute inset-0 bg-gradient-to-tr from-[#d4a853]/5 to-transparent pointer-events-none opacity-0 group-hover:opacity-100 transition-opacity duration-500" />
              <div className="relative z-10">
                <div className="text-[#d4a853] mb-6 inline-block group-hover:scale-110 transition-transform duration-[350ms]">
                  <Sparkles className="w-8 h-8" />
                </div>
                <h3 className="font-serif-cormorant text-2xl font-semibold mb-4 text-white group-hover:text-[#d4a853] transition-colors duration-300">The Solstice Tasting</h3>
                <p className="font-sans-inter text-xs lg:text-sm text-[#a8a19a] leading-relaxed mb-6 font-light">
                  Our flagship 10-course seasonal odyssey, mapping the sensory transit of arctic woodlands. Includes visual tours of the curing pantry.
                </p>
              </div>
              <button 
                onClick={() => { setIsReservationOpen(true); playSoundEffect('click'); setBookingData(prev => ({...prev, specialRequest: 'Solstice Tasting Experience'})); }}
                className="font-sans-inter text-[10px] tracking-[0.15em] uppercase text-[#d4a853] group-hover:text-white font-bold flex items-center space-x-2 transition-colors duration-300 pt-4 border-t border-[#d4a853]/20 relative z-10"
                onMouseEnter={() => { setCursorHovering(true); playSoundEffect('hover'); }}
                onMouseLeave={() => setCursorHovering(false)}
              >
                <span>Initiate &rarr;</span>
              </button>
            </div>

            {/* Experience Card 3 */}
            <div 
              onMouseMove={(e) => handleTiltMove(e, 'exp3')}
              onMouseLeave={() => handleTiltLeave('exp3')}
              className="group bg-[#121110]/90 backdrop-blur-md border border-[#d4a853]/30 p-8 rounded-2xl transition-all duration-500 hover:border-[#d4a853] hover:shadow-[0_0_35px_rgba(212,168,83,0.25)] hover:-translate-y-1.5 flex flex-col justify-between reveal-on-scroll relative overflow-hidden"
              style={{
                transform: `perspective(1000px) rotateX(${tiltState.exp3?.x || 0}deg) rotateY(${tiltState.exp3?.y || 0}deg)`,
              }}
            >
              <div className="absolute inset-0 bg-gradient-to-tr from-[#d4a853]/5 to-transparent pointer-events-none opacity-0 group-hover:opacity-100 transition-opacity duration-500" />
              <div className="relative z-10">
                <div className="text-[#d4a853] mb-6 inline-block group-hover:scale-110 transition-transform duration-[350ms]">
                  <Compass className="w-8 h-8" />
                </div>
                <h3 className="font-serif-cormorant text-2xl font-semibold mb-4 text-white group-hover:text-[#d4a853] transition-colors duration-300">Elemental Nectars</h3>
                <p className="font-sans-inter text-xs lg:text-sm text-[#a8a19a] leading-relaxed mb-6 font-light">
                  A carefully gathered flight of biodynamic wine ferments, birch saps, and rare glacial meads curated by our beverage architect.
                </p>
              </div>
              <button 
                onClick={() => { setIsReservationOpen(true); playSoundEffect('click'); setBookingData(prev => ({...prev, specialRequest: 'Elemental Nectars Flight'})); }}
                className="font-sans-inter text-[10px] tracking-[0.15em] uppercase text-[#d4a853] group-hover:text-white font-bold flex items-center space-x-2 transition-colors duration-300 pt-4 border-t border-[#d4a853]/20 relative z-10"
                onMouseEnter={() => { setCursorHovering(true); playSoundEffect('hover'); }}
                onMouseLeave={() => setCursorHovering(false)}
              >
                <span>Initiate &rarr;</span>
              </button>
            </div>
          </div>

          {/* Interactive Sommelier pairing selector */}
          <div className="bg-[#121110]/90 backdrop-blur-md border border-[#d4a853] rounded-3xl p-6 lg:p-10 flex flex-col lg:flex-row items-stretch gap-8 relative overflow-hidden shadow-2xl reveal-on-scroll">
            <div className="absolute top-0 left-0 w-1.5 h-full bg-[#d4a853]" />
            
            <div className="w-full lg:w-2/5 flex flex-col justify-center relative z-10">
              <span className="font-sans-inter text-[10px] tracking-[0.25em] uppercase text-[#d4a853] block mb-1 font-bold">Elemental Nectar Matcher</span>
              <h4 className="font-serif-cormorant text-2xl lg:text-3xl text-white font-semibold mb-4">Pair Your Alchemy Choice</h4>
              <p className="font-sans-inter text-xs text-[#a8a19a] leading-relaxed mb-6 font-light">
                Select one of our signature rustic dishes below to see the rare natural vintage suggested by our beverage director.
              </p>

              <div className="space-y-2">
                {[
                  { id: 'reindeer', label: 'Birch Consommé' },
                  { id: 'cod', label: 'Hay-Smoked Cod' },
                  { id: 'boar', label: 'Highland Elk Medallion' }
                ].map((dish) => (
                  <button
                    key={dish.id}
                    onClick={() => { setSelectedPairingDish(dish.id); playSoundEffect('click'); }}
                    className={`w-full text-left px-5 py-3.5 rounded-full text-xs font-sans-inter tracking-wider uppercase border transition-all duration-300 ${
                      selectedPairingDish === dish.id
                        ? 'bg-[#d4a853] text-[#0c0b0a] border-[#d4a853] font-bold shadow-md shadow-[0_4px_15px_rgba(212,168,83,0.3)]'
                        : 'bg-transparent text-[#f4f3f0] border-[#d4a853]/30 hover:border-[#d4a853]'
                    }`}
                    onMouseEnter={() => { setCursorHovering(true); playSoundEffect('hover'); }}
                    onMouseLeave={() => setCursorHovering(false)}
                  >
                    {dish.label}
                  </button>
                ))}
              </div>
            </div>

            <div className="w-full lg:w-3/5 bg-[#0c0b0a]/90 backdrop-blur-md border border-[#d4a853]/40 rounded-2xl p-6 flex flex-col md:flex-row items-center gap-6 relative shadow-inner z-10">
              <div className="w-24 h-40 flex items-center justify-center bg-[#1c1813] rounded-2xl border border-[#d4a853]/40 shrink-0 p-2 relative overflow-hidden group shadow-lg">
                <div className="absolute inset-0 bg-[#d4a853]/5 group-hover:bg-[#d4a853]/10 transition-colors duration-500" />
                <svg className="w-full h-full text-[#d4a853] relative z-10 animate-bounce" viewBox="0 0 100 200" fill="currentColor">
                  <path d="M42,20 L58,20 L58,50 L65,75 L65,190 L35,190 L35,75 L42,50 Z" opacity="0.15" />
                  <path d="M48,20 L52,20 L52,50 L60,70 L60,190 L40,190 L40,70 L48,50 Z" />
                  <rect x="42" y="80" width="16" height="30" fill="#d4a853" rx="1" />
                  <circle cx="50" cy="95" r="4" fill="#0c0b0a" />
                </svg>
              </div>

              <div>
                <span className="font-serif-cormorant italic text-[#d4a853] text-sm block mb-1 font-bold">Architect's Elemental Pairing</span>
                
                {selectedPairingDish === 'reindeer' && (
                  <div>
                    <h5 className="font-serif-cormorant text-xl lg:text-2xl font-bold text-white mb-2">2015 Cold-Pressed Cloudberry Mead</h5>
                    <p className="font-sans-inter text-xs text-[#a8a19a] font-light leading-relaxed mb-4">
                      The dry, crisp botanical honey nodes and raw acidic cloudberry profile of this limited-release wild craft perfectly offset the deep forest floor earthiness of our Fermented Birch sap soup.
                    </p>
                    <span className="font-sans-inter text-[9px] bg-[#d4a853]/15 text-[#d4a853] px-3.5 py-1.5 rounded-full tracking-wider uppercase font-bold border border-[#d4a853]/30">Troms, Norway</span>
                  </div>
                )}

                {selectedPairingDish === 'cod' && (
                  <div>
                    <h5 className="font-serif-cormorant text-xl lg:text-2xl font-bold text-white mb-2">2018 Gut Oggau 'Theodora' Weiss</h5>
                    <p className="font-sans-inter text-xs text-[#a8a19a] font-light leading-relaxed mb-4">
                      An unfiltered, structural amber blend carrying precise chalky minerals and citrus skin notes that effortlessly cut through the smoky hay and rich kelp dashi oils.
                    </p>
                    <span className="font-sans-inter text-[9px] bg-[#d4a853]/15 text-[#d4a853] px-3.5 py-1.5 rounded-full tracking-wider uppercase font-bold border border-[#d4a853]/30">Burgenland, Austria</span>
                  </div>
                )}

                {selectedPairingDish === 'boar' && (
                  <div>
                    <h5 className="font-serif-cormorant text-xl lg:text-2xl font-bold text-white mb-2">2012 Radikon 'Jakot' Friulano Amber</h5>
                    <p className="font-sans-inter text-xs text-[#a8a19a] font-light leading-relaxed mb-4">
                      Deep, prolonged skin contact yields heavy tannins, dried tea leaves, and wild honey undertones that beautifully harmonize with the dense spruce bark oils and roasted elk loin.
                    </p>
                    <span className="font-sans-inter text-[9px] bg-[#d4a853]/15 text-[#d4a853] px-3.5 py-1.5 rounded-full tracking-wider uppercase font-bold border border-[#d4a853]/30">Oslavia, Italy</span>
                  </div>
                )}
              </div>
            </div>
          </div>

        </div>
      </section>

      {/* Accolades marquee loop */}
      <section className="py-12 bg-[#121110] border-y border-[#d4a853]/30 overflow-hidden select-none relative">
        <div className="absolute top-0 left-0 right-0 h-[1px] bg-gradient-to-r from-transparent via-[#d4a853] to-transparent" />
        <div className="max-w-7xl mx-auto px-6 mb-4 text-center">
          <span className="font-sans-inter text-[10px] tracking-[0.3em] uppercase text-[#d4a853] font-bold">Mentions & Accolades</span>
        </div>
        
        <div className="relative w-full overflow-hidden flex whitespace-nowrap">
          <div className="animate-marquee py-2 flex items-center space-x-16 text-2xl md:text-3xl lg:text-4xl font-serif-cormorant italic text-[#f4f3f0]/30">
            <span>The Financial Times</span>
            <span className="text-[#d4a853] text-xl font-sans font-light">&bull;</span>
            <span>Wallpaper* Magazine</span>
            <span className="text-[#d4a853] text-xl font-sans font-light">&bull;</span>
            <span>Michelin Guide UK</span>
            <span className="text-[#d4a853] text-xl font-sans font-light">&bull;</span>
            <span>Condé Nast Traveler</span>
            <span className="text-[#d4a853] text-xl font-sans font-light">&bull;</span>
            <span>The Shetland Chronicles</span>
            <span className="text-[#d4a853] text-xl font-sans font-light">&bull;</span>
          </div>
          <div className="animate-marquee py-2 flex items-center space-x-16 text-2xl md:text-3xl lg:text-4xl font-serif-cormorant italic text-[#f4f3f0]/30" aria-hidden="true">
            <span>The Financial Times</span>
            <span className="text-[#d4a853] text-xl font-sans font-light">&bull;</span>
            <span>Wallpaper* Magazine</span>
            <span className="text-[#d4a853] text-xl font-sans font-light">&bull;</span>
            <span>Michelin Guide UK</span>
            <span className="text-[#d4a853] text-xl font-sans font-light">&bull;</span>
            <span>Condé Nast Traveler</span>
            <span className="text-[#d4a853] text-xl font-sans font-light">&bull;</span>
            <span>The Shetland Chronicles</span>
            <span className="text-[#d4a853] text-xl font-sans font-light">&bull;</span>
          </div>
        </div>
      </section>

      {}
      <section 
        id="testimonials" 
        className="py-24 lg:py-32 bg-[#0c0b0a] relative overflow-hidden"
      >
        {/* Full-bleed 3D background wrapper - High opacity firelight background */}
        <div 
          className="absolute inset-0 z-0 pointer-events-none select-none transition-transform duration-[150ms] ease-out scale-110"
          style={{
            transform: `perspective(1000px) translateY(${(smoothScrollY - 6800) * 0.12}px) rotateY(${mousePos.x * 5}deg) translateZ(-40px)`
          }}
        >
          <img 
            src="https://images.unsplash.com/photo-1504280390367-361c6d9f38f4?auto=format&fit=crop&q=80&w=1920" 
            alt="Logs Firelight Background" 
            className="absolute inset-0 w-full h-full object-cover opacity-55 filter brightness-[0.5] contrast-[1.25]"
          />
          <div className="absolute inset-0 bg-gradient-to-b from-[#121110]/95 via-transparent to-[#121110]/95" />
        </div>

        <div className="max-w-6xl mx-auto px-6 lg:px-12 relative z-20">
          
          <div className="text-center mb-16 reveal-on-scroll">
            <span className="font-sans-inter text-xs tracking-[0.2em] uppercase text-[#d4a853] block mb-2 font-bold bg-[#0c0b0a]/80 px-4 py-1.5 rounded-full border border-[#d4a853]/20 inline-block">Gathered Guest Journeys</span>
            <h2 className="font-serif-cormorant text-4xl lg:text-5xl font-semibold text-white inline-block relative pb-4 mt-3">
              Guest Chronicles
              <span className="absolute bottom-0 left-1/4 right-1/4 h-0.5 bg-gradient-to-r from-transparent via-[#d4a853] to-transparent" />
            </h2>
          </div>

          <div className="grid grid-cols-1 md:grid-cols-3 gap-8">
            
            <div className="bg-[#121110]/95 backdrop-blur-md border border-[#d4a853]/30 p-8 rounded-2xl flex flex-col justify-between relative transition-all duration-300 hover:-translate-y-2 hover:border-[#d4a853] hover:shadow-[0_4px_25px_rgba(212,168,83,0.15)] reveal-on-scroll">
              <div>
                <div className="flex space-x-1 mb-6 text-[#d4a853]">
                  {[...Array(5)].map((_, i) => (
                    <svg key={i} className="w-4 h-4 fill-current" viewBox="0 0 20 20">
                      <path d="M9.049 2.927c.3-.921 1.603-.921 1.902 0l1.07 3.292a1 1 0 00.95.69h3.462c.969 0 1.371 1.24.588 1.81l-2.8 2.034a1 1 0 00-.364 1.118l1.07 3.292c.3.921-.755 1.688-1.54 1.118l-2.8-2.034a1 1 0 00-1.175 0l-2.8 2.034c-.784.57-1.838-.197-1.539-1.118l1.07-3.292a1 1 0 00-.364-1.118L2.98 8.72c-.783-.57-.38-1.81.588-1.81h3.461a1 1 0 00.951-.69l1.07-3.292z" />
                    </svg>
                  ))}
                </div>
                <p className="font-serif-cormorant italic text-lg text-[#f4f3f0] leading-relaxed mb-6 font-light">
                  "The Solstice tasting menu was like traversing a deep, foggy evergreen forest at midnight. The sheer purity of flavor extracted from scorched wild lichen and birch sap is culinary magic."
                </p>
              </div>
              <div className="border-t border-[#d4a853]/20 pt-4 mt-2">
                <span className="font-sans-inter text-xs text-white block font-bold">Henrik S.</span>
                <span className="font-sans-inter text-[10px] text-[#d4a853] block uppercase tracking-widest mt-0.5 font-bold">Visited February 2026</span>
              </div>
            </div>

            <div className="bg-[#121110]/95 backdrop-blur-md border border-[#d4a853]/30 p-8 rounded-2xl flex flex-col justify-between relative transition-all duration-300 hover:-translate-y-2 hover:border-[#d4a853] hover:shadow-[0_4px_25px_rgba(212,168,83,0.15)] reveal-on-scroll">
              <div>
                <div className="flex space-x-1 mb-6 text-[#d4a853]">
                  {[...Array(5)].map((_, i) => (
                    <svg key={i} className="w-4 h-4 fill-current" viewBox="0 0 20 20">
                      <path d="M9.049 2.927c.3-.921 1.603-.921 1.902 0l1.07 3.292a1 1 0 00.95.69h3.462c.969 0 1.371 1.24.588 1.81l-2.8 2.034a1 1 0 00-.364 1.118l1.07 3.292c.3.921-.755 1.688-1.54 1.118l-2.8-2.034a1 1 0 00-1.175 0l-2.8 2.034c-.784.57-1.838-.197-1.539-1.118l1.07-3.292a1 1 0 00-.364-1.118L2.98 8.72c-.783-.57-.38-1.81.588-1.81h3.461a1 1 0 00.951-.69l1.07-3.292z" />
                    </svg>
                  ))}
                </div>
                <p className="font-serif-cormorant italic text-lg text-[#f4f3f0] leading-relaxed mb-6 font-light">
                  "VALO is an absolute sensory masterpiece. The open hearth table is a magnificent encounter with fire and flavor. It is a stunning, sophisticated, and incredibly warm addition to Bruton Place."
                </p>
              </div>
              <div className="border-t border-[#d4a853]/20 pt-4 mt-2">
                <span className="font-sans-inter text-xs text-white block font-bold">Dr. Clara Vance</span>
                <span className="font-sans-inter text-[10px] text-[#d4a853] block uppercase tracking-widest mt-0.5 font-bold">Visited May 2026</span>
              </div>
            </div>

            <div className="bg-[#121110]/95 backdrop-blur-md border border-[#d4a853]/30 p-8 rounded-2xl flex flex-col justify-between relative transition-all duration-300 hover:-translate-y-2 hover:border-[#d4a853] hover:shadow-[0_4px_25px_rgba(212,168,83,0.15)] reveal-on-scroll">
              <div>
                <div className="flex space-x-1 mb-6 text-[#d4a853]">
                  {[...Array(5)].map((_, i) => (
                    <svg key={i} className="w-4 h-4 fill-current" viewBox="0 0 20 20">
                      <path d="M9.049 2.927c.3-.921 1.603-.921 1.902 0l1.07 3.292a1 1 0 00.95.69h3.462c.969 0 1.371 1.24.588 1.81l-2.8 2.034a1 1 0 00-.364 1.118l1.07 3.292c.3.921-.755 1.688-1.54 1.118l-2.8-2.034a1 1 0 00-1.175 0l-2.8 2.034c-.784.57-1.838-.197-1.539-1.118l1.07-3.292a1 1 0 00-.364-1.118L2.98 8.72c-.783-.57-.38-1.81.588-1.81h3.461a1 1 0 00.951-.69l1.07-3.292z" />
                    </svg>
                  ))}
                </div>
                <p className="font-serif-cormorant italic text-lg text-[#f4f3f0] leading-relaxed mb-6 font-light">
                  "An untamed, exquisite, yet elegant love letter to the rugged north. Chef Elina Kannel is a true pioneer. Watching her work over the live birch wood fires is a spiritual experience."
                </p>
              </div>
              <div className="border-t border-[#d4a853]/20 pt-4 mt-2">
                <span className="font-sans-inter text-xs text-white block font-bold">Sir Alistair M.</span>
                <span className="font-sans-inter text-[10px] text-[#d4a853] block uppercase tracking-widest mt-0.5 font-bold">Visited June 2026</span>
              </div>
            </div>

          </div>
        </div>
      </section>

      {}
      <section 
        id="reserve" 
        className="relative py-28 bg-[#121110] border-y border-[#d4a853]/30 overflow-hidden"
      >
        {/* Full-bleed 3D background wrapper - High opacity roaring flames visible */}
        <div 
          className="absolute inset-0 z-0 pointer-events-none select-none transition-transform duration-[150ms] ease-out scale-110"
          style={{
            transform: `perspective(1000px) translateY(${(smoothScrollY - 7400) * -0.1}px) rotateY(${mousePos.x * -4}deg) translateZ(-40px)`
          }}
        >
          <img 
            src="https://images.unsplash.com/photo-1508873696983-2df519f0397e?auto=format&fit=crop&q=80&w=1920" 
            alt="Flames Background Layout" 
            className="absolute inset-0 w-full h-full object-cover opacity-55 filter brightness-[0.55] contrast-[1.35]"
          />
          <div className="absolute inset-0 bg-gradient-to-b from-[#0c0b0a]/95 via-transparent to-[#0c0b0a]/95" />
        </div>

        <div className="absolute inset-0 pointer-events-none opacity-[0.04] bg-repeat z-10" 
             style={{ backgroundImage: `url("data:image/svg+xml,%3Csvg viewBox='0 0 200 200' xmlns='http://www.w3.org/2000/svg'%3E%3Cfilter id='noise'%3E%3CfeTurbulence type='fractalNoise' baseFrequency='0.65' numOctaves='3' stitchTiles='stitch'/%3E%3C/filter%3E%3Crect width='100%25' height='100%25' filter='url(%23noise)'/%3E%3C/svg%3E")` }} />
        
        <div className="absolute -bottom-24 left-1/2 transform -translate-x-1/2 w-[600px] h-60 bg-[#d4a853]/10 rounded-full filter blur-[120px] pointer-events-none z-10" />

        <div className="max-w-4xl mx-auto px-6 text-center relative z-20 space-y-8 reveal-on-scroll bg-[#0c0b0a]/80 backdrop-blur-md p-10 lg:p-14 rounded-3xl border border-[#d4a853]/25 shadow-2xl">
          <span className="font-sans-inter text-xs tracking-[0.25em] uppercase text-[#d4a853] font-bold bg-[#0c0b0a] px-4 py-1.5 rounded-full border border-[#d4a853]/35 inline-block">Elemental Encounters</span>
          
          <h2 className="font-serif-cormorant text-4xl lg:text-6xl font-semibold text-white tracking-tight leading-none mt-3">
            Claim Your Hearth Seat
          </h2>
          
          <p className="font-sans-inter font-light text-[#a8a19a] max-w-lg mx-auto text-sm lg:text-base leading-relaxed">
            We strongly encourage booking 3–5 weeks in advance for our seasonal weekend fireside events. For bespoke gatherings of 8 or more, contact our curator.
          </p>

          <div className="pt-4">
            <button
              onClick={() => { setIsReservationOpen(true); playSoundEffect('click'); }}
              className="font-sans-inter text-xs tracking-[0.2em] uppercase bg-gradient-to-r from-[#d4a853] via-[#ffda85] to-[#bda043] text-[#0c0b0a] font-bold px-12 py-5 rounded-full transition-all duration-300 transform hover:-translate-y-1 hover:shadow-[0_10px_30px_rgba(212,168,83,0.4)] border border-[#ffea9f]/40 inline-flex items-center space-x-2"
              onMouseEnter={() => { setCursorHovering(true); playSoundEffect('hover'); }}
              onMouseLeave={() => setCursorHovering(false)}
            >
              <span>Cross the Threshold &rarr;</span>
            </button>
          </div>

          <div className="text-xs font-sans-inter text-[#a8a19a] pt-2">
            Speak directly with our Hostess at Bruton Place: <span className="text-[#d4a853] font-bold">+44 20 8987 6543</span>
          </div>
        </div>
      </section>

      {/* Footer Details */}
      <footer className="bg-[#0c0b0a] text-[#a8a19a] pt-20 pb-10 border-t border-[#d4a853]/20 relative z-20">
        <div className="max-w-7xl mx-auto px-6 lg:px-12 grid grid-cols-1 md:grid-cols-4 gap-12 mb-16">
          
          <div className="space-y-4 md:col-span-1">
            <h3 className="font-serif-cormorant text-2xl italic font-bold text-[#d4a853] tracking-wider">VALO</h3>
            <p className="font-sans-inter text-xs leading-relaxed font-light">
              Modern Nordic & Foraged Fire gastronomy situated in the elegant, historic heart of Mayfair, London.
            </p>
            <div className="flex space-x-4 pt-2">
              <a href="#" className="hover:text-[#d4a853] transition-colors duration-300">
                <span className="text-xs font-sans-inter tracking-wider">Instagram</span>
              </a>
              <a href="#" className="hover:text-[#d4a853] transition-colors duration-300">
                <span className="text-xs font-sans-inter tracking-wider">Vimeo Journal</span>
              </a>
            </div>
          </div>

          <div className="space-y-4">
            <h4 className="font-sans-inter text-xs tracking-[0.15em] uppercase text-white font-bold">The Elemental Cycles</h4>
            <div className="space-y-2 font-sans-inter text-xs font-light">
              <p className="flex justify-between"><span>Wednesday – Sunday:</span> <span className="text-white font-medium">17:30 – 23:30</span></p>
              <p className="flex justify-between"><span>Monday – Tuesday:</span> <span className="text-[#d4a853] font-bold italic">Curing & Preservation</span></p>
              <p className="pt-2 text-[11px] text-[#a8a19a]">Last seasonal tasting seating begins at 21:00.</p>
            </div>
          </div>

          <div className="space-y-4">
            <h4 className="font-sans-inter text-xs tracking-[0.15em] uppercase text-white font-bold">Enquiries</h4>
            <div className="space-y-2 font-sans-inter text-xs font-light">
              <p className="text-white font-medium">Phone: +44 20 8987 6543</p>
              <p>Email: hearth@valolondon.com</p>
              <p>Bespoke Events: curators@valolondon.com</p>
            </div>
          </div>

          <div className="space-y-4">
            <h4 className="font-sans-inter text-xs tracking-[0.15em] uppercase text-white font-bold">Bruton Outpost</h4>
            <p className="font-sans-inter text-xs font-light leading-relaxed">
              42 Bruton Place, Mayfair<br />
              London, W1J 6NP<br />
              United Kingdom
            </p>
            <a 
              href="https://maps.google.com" 
              target="_blank" 
              rel="noopener noreferrer" 
              className="font-sans-inter text-xs text-[#d4a853] hover:text-white transition-colors duration-300 flex items-center space-x-1 font-bold"
            >
              <span>Map coordinates</span>
              <span>&rarr;</span>
            </a>
          </div>

        </div>

        <div className="max-w-7xl mx-auto px-6 lg:px-12 border-t border-[#d4a853]/20 pt-8 flex flex-col md:flex-row items-center justify-between text-xs font-sans-inter font-light">
          <p className="mb-4 md:mb-0">&copy; 2026 VALO Restaurant Ltd. All rights reserved.</p>
          <div className="flex space-x-6 text-[11px]">
            <a href="#" className="hover:text-[#d4a853]">Ethical Sourcing Protocol</a>
            <a href="#" className="hover:text-[#d4a853]">Hearth Terms</a>
            <a href="#" className="hover:text-[#d4a853]">Accessibility Standards</a>
          </div>
        </div>
      </footer>

      {}
      {isReservationOpen && (
        <div className="fixed inset-0 z-[999] flex items-center justify-center p-4 animate-fade-in">
          <div 
            className="absolute inset-0 bg-[#0c0b0a]/95 backdrop-blur-md"
            onClick={resetBookingForm}
          />
          
          <div className="relative bg-[#121110] border-2 border-[#d4a853] w-full max-w-xl max-h-[90vh] overflow-y-auto z-10 shadow-[0_0_50px_rgba(212,168,83,0.4)] p-6 lg:p-10 text-left rounded-3xl">
            
            <button 
              onClick={resetBookingForm}
              className="absolute top-4 right-4 text-[#a8a19a] hover:text-white p-2.5 border border-[#d4a853]/30 rounded-full bg-[#1c1813]"
              aria-label="Close modal"
            >
              <svg className="w-5 h-5" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                <path strokeLinecap="round" strokeLinejoin="round" strokeWidth={1.5} d="M6 18L18 6M6 6l12 12" />
              </svg>
            </button>

            {!bookingSuccess ? (
              <div>
                <div className="flex items-center space-x-4 mb-8">
                  <div className={`flex items-center justify-center w-9 h-9 rounded-full border text-xs font-sans-inter font-bold transition-all duration-300 ${reservationStep >= 1 ? 'border-[#d4a853] bg-gradient-to-r from-[#d4a853] to-[#bda043] text-[#0c0b0a] shadow-lg shadow-[#d4a853]/25' : 'border-[#d4a853]/30 text-[#a8a19a]'}`}>1</div>
                  <div className="h-0.5 bg-[#d4a853]/20 flex-1" />
                  <div className={`flex items-center justify-center w-9 h-9 rounded-full border text-xs font-sans-inter font-bold transition-all duration-300 ${reservationStep >= 2 ? 'border-[#d4a853] bg-gradient-to-r from-[#d4a853] to-[#bda043] text-[#0c0b0a] shadow-lg shadow-[#d4a853]/25' : 'border-[#d4a853]/30 text-[#a8a19a]'}`}>2</div>
                  <div className="h-0.5 bg-[#d4a853]/20 flex-1" />
                  <div className={`flex items-center justify-center w-9 h-9 rounded-full border text-xs font-sans-inter font-bold transition-all duration-300 ${reservationStep >= 3 ? 'border-[#d4a853] bg-gradient-to-r from-[#d4a853] to-[#bda043] text-[#0c0b0a] shadow-lg shadow-[#d4a853]/25' : 'border-[#d4a853]/30 text-[#a8a19a]'}`}>3</div>
                </div>

                <h3 className="font-serif-cormorant text-3xl font-bold text-[#d4a853] mb-2 text-center italic text-shadow-glow">
                  Solstice Seating Registration
                </h3>
                <p className="font-sans-inter text-xs text-[#a8a19a] text-center mb-8 font-light">
                  Align with Chef Elina Kannel for a magnificent dining experience
                </p>

                <form onSubmit={handleConfirmBooking} className="space-y-6">
                  
                  {/* STEP 1: Date, Guests, Time */}
                  {reservationStep === 1 && (
                    <div className="space-y-5">
                      <div>
                        <label className="block text-xs font-sans-inter tracking-wider uppercase text-white mb-2 font-bold">Hearth Assembly Count</label>
                        <select 
                          name="guests" 
                          value={bookingData.guests}
                          onChange={handleBookingInputChange}
                          className="w-full bg-[#0c0b0a] border border-[#d4a853]/40 text-white p-3.5 font-sans-inter text-sm rounded-xl focus:outline-none focus:border-[#d4a853]"
                        >
                          <option value="1">1 Seeker</option>
                          <option value="2">2 Seekers</option>
                          <option value="3">3 Seekers</option>
                          <option value="4">4 Seekers</option>
                          <option value="5">5 Seekers</option>
                          <option value="6">6 Seekers</option>
                          <option value="7">7 Seekers</option>
                          <option value="8">8 Seekers (Feast Table)</option>
                        </select>
                      </div>

                      <div className="grid grid-cols-1 sm:grid-cols-2 gap-4">
                        <div>
                          <label className="block text-xs font-sans-inter tracking-wider uppercase text-white mb-2 font-bold">Chosen Sun Cycle Date</label>
                          <input 
                            type="date" 
                            name="date"
                            value={bookingData.date}
                            onChange={handleBookingInputChange}
                            className="w-full bg-[#0c0b0a] border border-[#d4a853]/40 text-white p-3.5 font-sans-inter text-sm rounded-xl focus:outline-none focus:border-[#d4a853]"
                          />
                        </div>
                        <div>
                          <label className="block text-xs font-sans-inter tracking-wider uppercase text-white mb-2 font-bold">Hour of Dusk Seating</label>
                          <select 
                            name="time"
                            value={bookingData.time}
                            onChange={handleBookingInputChange}
                            className="w-full bg-[#0c0b0a] border border-[#d4a853]/40 text-white p-3.5 font-sans-inter text-sm rounded-xl focus:outline-none focus:border-[#d4a853]"
                          >
                            <option value="17:30">17:30 (Twilight Spark)</option>
                            <option value="18:00">18:00</option>
                            <option value="18:30">18:30</option>
                            <option value="19:00">19:00 (Hearth Peak Hour)</option>
                            <option value="19:30">19:30</option>
                            <option value="20:00">20:00</option>
                            <option value="20:30">20:30 (Midnight Ember Seating)</option>
                          </select>
                        </div>
                      </div>

                      <div className="pt-4 flex justify-end">
                        <button
                          type="button"
                          onClick={handleNextStep}
                          className="w-full sm:w-auto bg-gradient-to-r from-[#d4a853] to-[#bda043] text-[#0c0b0a] text-xs font-sans-inter font-bold uppercase tracking-wider px-9 py-4 rounded-full transition-all duration-300"
                        >
                          Progress Registry &rarr;
                        </button>
                      </div>
                    </div>
                  )}

                  {/* STEP 2: Client Info */}
                  {reservationStep === 2 && (
                    <div className="space-y-5">
                      <div>
                        <label className="block text-xs font-sans-inter tracking-wider uppercase text-white mb-2 font-bold">Your Noble Name</label>
                        <input 
                          type="text" 
                          name="name"
                          required
                          placeholder="Your full name"
                          value={bookingData.name}
                          onChange={handleBookingInputChange}
                          className="w-full bg-[#0c0b0a] border border-[#d4a853]/40 text-white p-3.5 font-sans-inter text-sm rounded-xl focus:outline-none focus:border-[#d4a853]"
                        />
                      </div>

                      <div className="grid grid-cols-1 sm:grid-cols-2 gap-4">
                        <div>
                          <label className="block text-xs font-sans-inter tracking-wider uppercase text-white mb-2 font-bold">Electronic Mail Address</label>
                          <input 
                            type="email" 
                            name="email"
                            required
                            placeholder="you@domain.com"
                            value={bookingData.email}
                            onChange={handleBookingInputChange}
                            className="w-full bg-[#0c0b0a] border border-[#d4a853]/40 text-white p-3.5 font-sans-inter text-sm rounded-xl focus:outline-none focus:border-[#d4a853]"
                          />
                        </div>
                        <div>
                          <label className="block text-xs font-sans-inter tracking-wider uppercase text-white mb-2 font-bold">Direct Contact Number</label>
                          <input 
                            type="tel" 
                            name="phone"
                            required
                            placeholder="+44 7123 4567"
                            value={bookingData.phone}
                            onChange={handleBookingInputChange}
                            className="w-full bg-[#0c0b0a] border border-[#d4a853]/40 text-white p-3.5 font-sans-inter text-sm rounded-xl focus:outline-none focus:border-[#d4a853]"
                          />
                        </div>
                      </div>

                      <div>
                        <label className="block text-xs font-sans-inter tracking-wider uppercase text-white mb-2 font-bold">Allergies / Dietary Restrictions (Optional)</label>
                        <input 
                          type="text" 
                          name="dietary"
                          placeholder="e.g. Foraging allergies, vegan parameters"
                          value={bookingData.dietary}
                          onChange={handleBookingInputChange}
                          className="w-full bg-[#0c0b0a] border border-[#d4a853]/40 text-[#a8a19a] p-3.5 font-sans-inter text-sm rounded-xl focus:outline-none focus:border-[#d4a853]"
                        />
                      </div>

                      <div className="pt-4 flex justify-between space-x-4">
                        <button
                          type="button"
                          onClick={handlePrevStep}
                          className="border border-[#d4a853]/30 text-[#a8a19a] hover:text-white text-xs font-sans-inter font-bold uppercase tracking-wider px-6 py-3.5 rounded-full transition-all duration-300 bg-[#1c1813]"
                        >
                          Step Back
                        </button>
                        <button
                          type="button"
                          onClick={handleNextStep}
                          className="bg-gradient-to-r from-[#d4a853] to-[#bda043] text-[#0c0b0a] text-xs font-sans-inter font-bold uppercase tracking-wider px-9 py-4 rounded-full transition-all duration-300"
                          disabled={!bookingData.name || !bookingData.email || !bookingData.phone}
                        >
                          Verify Summary &rarr;
                        </button>
                      </div>
                    </div>
                  )}

                  {/* STEP 3: Confirm Summary details */}
                  {reservationStep === 3 && (
                    <div className="space-y-6">
                      <div className="bg-[#0c0b0a] border border-[#d4a853]/40 p-5 space-y-3 rounded-2xl shadow-inner">
                        <span className="font-sans-inter text-[10px] tracking-wider uppercase text-[#d4a853] font-bold block">Hearth Registry Summary</span>
                        
                        <div className="grid grid-cols-2 gap-y-2 text-xs font-sans-inter leading-relaxed">
                          <span className="text-[#a8a19a]">Assembly Size:</span>
                          <span className="text-white font-bold text-right">{bookingData.guests} Seekers</span>

                          <span className="text-[#a8a19a]">Cycle & Hour:</span>
                          <span className="text-white font-bold text-right">{bookingData.date} at {bookingData.time}</span>

                          <span className="text-[#a8a19a]">Registry Holder:</span>
                          <span className="text-white font-bold text-right">{bookingData.name}</span>

                          {bookingData.dietary && (
                            <>
                              <span className="text-[#a8a19a]">Dietary constraints:</span>
                              <span className="text-[#d4a853] font-bold text-right">{bookingData.dietary}</span>
                            </>
                          )}

                          {bookingData.specialRequest && (
                            <>
                              <span className="text-[#a8a19a]">Initiated Ritual:</span>
                              <span className="text-[#d4a853] font-bold text-right">{bookingData.specialRequest}</span>
                            </>
                          )}
                        </div>
                      </div>

                      <label className="flex items-start space-x-3 cursor-pointer select-none">
                        <input 
                          type="checkbox" 
                          name="agreedToTerms"
                          required
                          checked={bookingData.agreedToTerms}
                          onChange={handleBookingInputChange}
                          className="mt-1 accent-[#d4a853]"
                        />
                        <span className="font-sans-inter text-[11px] text-[#a8a19a] leading-normal font-light">
                          I fully understand and accept VALO's hearth protocol. Cancellations must be made at least 48 hours in advance to respect limited local micro-foraging supplies.
                        </span>
                      </label>

                      <div className="pt-4 flex justify-between space-x-4">
                        <button
                          type="button"
                          onClick={handlePrevStep}
                          className="border border-[#d4a853]/30 text-[#a8a19a] hover:text-white text-xs font-sans-inter font-bold uppercase tracking-wider px-6 py-3.5 rounded-full transition-all duration-300 bg-[#1c1813]"
                        >
                          Step Back
                        </button>
                        <button
                          type="submit"
                          disabled={!bookingData.agreedToTerms}
                          className="flex-1 bg-gradient-to-r from-[#d4a853] to-[#bda043] disabled:from-[#121110] disabled:to-[#121110] disabled:text-[#a8a19a] disabled:cursor-not-allowed text-[#0c0b0a] text-xs font-sans-inter font-bold uppercase tracking-wider py-4 text-center rounded-full transition-all duration-300 border border-[#ffea9f]/40"
                        >
                          Forge Registry &rarr;
                        </button>
                      </div>
                    </div>
                  )}

                </form>
              </div>
            ) : (
              /* Success confirmation panel view */
              <div className="text-center py-10 space-y-6">
                <div className="w-16 h-16 bg-[#d4a853]/15 border-2 border-[#d4a853] rounded-full flex items-center justify-center mx-auto text-[#d4a853] animate-bounce shadow-[0_4px_15px_rgba(212,168,83,0.3)]">
                  <svg className="w-8 h-8" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                    <path strokeLinecap="round" strokeLinejoin="round" strokeWidth={2} d="M5 13l4 4L19 7" />
                  </svg>
                </div>

                <div className="space-y-2">
                  <h3 className="font-serif-cormorant text-3xl font-bold text-white">Registry Forged</h3>
                  <p className="font-sans-inter text-xs text-[#a8a19a] font-light max-w-sm mx-auto">
                    Welcome to the elemental circle, {bookingData.name}. We look forward to hosting your assembly at the open fires of VALO.
                  </p>
                </div>

                <div className="bg-[#0c0b0a] border border-[#d4a853] p-4 max-w-xs mx-auto rounded-2xl shadow-xl">
                  <span className="font-sans-inter text-[10px] tracking-widest uppercase text-[#a8a19a] block mb-1">Ember Confirmation Code</span>
                  <span className="font-sans-inter text-base tracking-widest text-[#d4a853] font-bold uppercase">VL-{(Math.floor(100000 + Math.random() * 900000))}</span>
                </div>

                <div className="text-xs font-sans-inter text-[#a8a19a] space-y-1">
                  <p>A dispatch notice has been routed to your beacon: <span className="text-white font-medium">{bookingData.email}</span></p>
                  <p>Assembly size: <span className="text-white font-bold">{bookingData.guests} Seekers</span> · Solstice Date: <span className="text-white font-bold">{bookingData.date} at {bookingData.time}</span></p>
                </div>

                <button
                  onClick={resetBookingForm}
                  className="bg-gradient-to-r from-[#d4a853] to-[#bda043] text-[#0c0b0a] text-xs font-sans-inter font-bold uppercase tracking-wider px-9 py-4 rounded-full transition-all duration-300"
                >
                  Conclude Seating Registry
                </button>
              </div>
            )}

          </div>
        </div>
      )}

    </div>
  );
}
