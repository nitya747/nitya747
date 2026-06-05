```aura width=860 height=200
<div style={{
  width: '100%', height: '100%', background: '#0d0b12',
  display: 'flex', alignItems: 'center', fontFamily: 'Inter',
  position: 'relative', overflow: 'hidden', borderRadius: 16,
  border: '1px solid rgba(236, 72, 153, 0.16)'
}}>
<style>
{`
  @keyframes drift1 { 0%,100%{transform:translate(0,0)} 50%{transform:translate(30px,-15px)} }
  @keyframes drift2 { 0%,100%{transform:translate(0,0)} 50%{transform:translate(-40px,20px)} }
  @keyframes drift3 { 0%,100%{transform:translate(0,0)} 50%{transform:translate(25px,10px)} }
  @keyframes pulse { 0%,100%{opacity:0.1;transform:scale(0.8)} 50%{opacity:0.8;transform:scale(1.2)} }
  @keyframes flow { 0%{transform:translateX(-20%);opacity:0} 20%{opacity:0.2} 80%{opacity:0.2} 100%{transform:translateX(100%);opacity:0} }
`}
</style>
<svg width="860" height="200" style={{ position: 'absolute', top: 0, left: 0 }}>
  <defs>
    <radialGradient id="n1" cx="50%" cy="50%" r="50%"><stop offset="0%" stopColor="rgba(236, 72, 153, 0.18)" /><stop offset="100%" stopColor="rgba(236, 72, 153, 0)" /></radialGradient>
    <radialGradient id="n2" cx="50%" cy="50%" r="50%"><stop offset="0%" stopColor="rgba(147, 51, 234, 0.16)" /><stop offset="100%" stopColor="rgba(147, 51, 234, 0)" /></radialGradient>
    <radialGradient id="n3" cx="50%" cy="50%" r="50%"><stop offset="0%" stopColor="rgba(255, 255, 255, 0.06)" /><stop offset="100%" stopColor="rgba(255, 255, 255, 0)" /></radialGradient>
  </defs>
  
  <g>
    <circle cx="80" cy="30" r="1.5" fill="#fff" style={{animation: 'pulse 3s infinite'}} />
    <circle cx="250" cy="170" r="2" fill="#fff" style={{animation: 'pulse 4s infinite 1s'}} />
    <circle cx="480" cy="50" r="1.5" fill="#fff" style={{animation: 'pulse 5s infinite 2s'}} />
    <circle cx="720" cy="160" r="1" fill="#fff" style={{animation: 'pulse 3.5s infinite 0.5s'}} />
    <circle cx="820" cy="40" r="2" fill="#fff" style={{animation: 'pulse 4.5s infinite 1.5s'}} />
  </g>

  <g stroke="rgba(255, 255, 255, 0.12)" strokeWidth="1" fill="none">
    <path d="M0,70 Q200,90 400,50 T860,70" style={{animation: 'flow 14s linear infinite'}} />
    <path d="M0,150 Q300,120 500,160 T860,140" style={{animation: 'flow 18s linear infinite 3s'}} />
  </g>

  <g style={{ animation: 'drift1 24s ease-in-out infinite' }}>
    <ellipse cx="160" cy="100" rx="140" ry="70" fill="url(#n1)" />
    <ellipse cx="120" cy="80" rx="90" ry="40" fill="url(#n1)" />
  </g>
  <g style={{ animation: 'drift2 28s ease-in-out infinite' }}>
    <ellipse cx="700" cy="110" rx="150" ry="75" fill="url(#n2)" />
    <ellipse cx="640" cy="90" rx="100" ry="45" fill="url(#n2)" />
  </g>
  <g style={{ animation: 'drift3 22s ease-in-out infinite' }}>
    <ellipse cx="430" cy="40" rx="110" ry="50" fill="url(#n3)" />
  </g>
</svg>

<div style={{
  position: 'absolute', left: 48, top: 52, width: 96, height: 96,
  borderRadius: 48, background: 'linear-gradient(135deg, rgba(236,72,153,0.5), rgba(139,92,246,0.5))',
  display: 'flex', alignItems: 'center', justifyContent: 'center',
}}>
  <img src={(github && github.user && github.user.avatarUrl) || 'https://github.githubassets.com/images/modules/logos_page/GitHub-Mark.png'} width={88} height={88} style={{ borderRadius: 44 }} />
</div>

<div style={{ display:'flex', flexDirection:'column', marginLeft:168, gap:8, zIndex: 10 }}>
  <div style={{ display:'flex', fontSize:38, fontWeight:800, color:'#ffffff', letterSpacing:'-1px', lineHeight:1 }}>
    Nitya Arora
  </div>
  <div style={{ display:'flex', fontSize:15, color:'rgba(255, 185, 230, 0.85)', fontWeight:400, letterSpacing:'0.3px' }}>
    Turning Ideas Into Products
  </div>
  <div style={{ display:'flex', gap:8, marginTop:6 }}>
    {['Frontend', 'Full Stack', 'Product Builder'].map(function(tag) {
      return (<div key={tag} style={{ display:'flex', padding:'4px 12px', borderRadius:20, background:'rgba(236,72,153,0.06)', border:'1px solid rgba(236,72,153,0.25)', color:'rgba(255,200,240,0.85)', fontSize:12, fontWeight:600 }}>{tag}</div>);
    })}
  </div>
</div>
</div>
```

```aura width=860 height=280
(function() {
  var categories = [
    { title: 'Languages', color: '#db2777', items: ['C++', 'Python', 'JavaScript'] },
    { title: 'Frontend', color: '#ec4899', items: ['React', 'HTML', 'CSS', 'Tailwind CSS'] },
    { title: 'Backend', color: '#9333ea', items: ['Node.js', 'Express.js'] },
    { title: 'Database & Infra', color: '#a855f7', items: ['Supabase', 'Firebase'] },
    { title: 'AI & Tools', color: '#f472b6', items: ['OpenAI', 'Git', 'GitHub'] },
  ];
  return (
    <div style={{
      width: '100%', height: '100%', background: '#0d0b12',
      display: 'flex', flexDirection: 'column', fontFamily: 'Inter', padding: '32px 32px', gap: 18,
      borderRadius: 16, border: '1px solid rgba(236, 72, 153, 0.16)', position: 'relative', overflow: 'hidden',
    }}>
    <style>{`
      @keyframes driftX { 0%,100%{transform:translate(0,0)} 50%{transform:translate(40px,-20px)} }
      @keyframes driftY { 0%,100%{transform:translate(0,0)} 50%{transform:translate(-50px,30px)} }
      @keyframes driftZ { 0%,100%{transform:translate(0,0)} 50%{transform:translate(30px,25px)} }
      @keyframes pulse { 0%,100%{opacity:0.1;transform:scale(0.8)} 50%{opacity:0.8;transform:scale(1.2)} }
      @keyframes flowSlow { 0%{transform:translateX(-10%);opacity:0} 20%{opacity:0.12} 80%{opacity:0.12} 100%{transform:translateX(100%);opacity:0} }
    `}</style>
    <svg width="860" height="280" style={{ position: 'absolute', top: 0, left: 0 }}>
      <defs>
        <radialGradient id="n6" cx="50%" cy="50%" r="50%"><stop offset="0%" stopColor="rgba(236, 72, 153, 0.15)" /><stop offset="100%" stopColor="rgba(236, 72, 153, 0)" /></radialGradient>
        <radialGradient id="n7" cx="50%" cy="50%" r="50%"><stop offset="0%" stopColor="rgba(147, 51, 234, 0.15)" /><stop offset="100%" stopColor="rgba(147, 51, 234, 0)" /></radialGradient>
        <radialGradient id="n8" cx="50%" cy="50%" r="50%"><stop offset="0%" stopColor="rgba(255, 255, 255, 0.04)" /><stop offset="100%" stopColor="rgba(255, 255, 255, 0)" /></radialGradient>
      </defs>

      <g>
        <circle cx="90" cy="50" r="2" fill="#fff" style={{animation: 'pulse 4s infinite'}} />
        <circle cx="320" cy="210" r="1.5" fill="#fff" style={{animation: 'pulse 3s infinite 1s'}} />
        <circle cx="550" cy="80" r="2" fill="#fff" style={{animation: 'pulse 5s infinite 2s'}} />
        <circle cx="780" cy="240" r="1.5" fill="#fff" style={{animation: 'pulse 3.5s infinite 0.5s'}} />
      </g>

      <g stroke="rgba(255,255,255,0.1)" strokeWidth="1" fill="none">
        <path d="M0,100 Q200,130 400,80 T860,110" style={{animation: 'flowSlow 22s linear infinite'}} />
        <path d="M0,220 Q300,190 500,240 T860,210" style={{animation: 'flowSlow 28s linear infinite 5s'}} />
      </g>

      <g style={{ animation: 'driftX 30s ease-in-out infinite' }}>
        <ellipse cx="200" cy="180" rx="160" ry="80" fill="url(#n6)" />
      </g>
      <g style={{ animation: 'driftY 34s ease-in-out infinite' }}>
        <ellipse cx="680" cy="200" rx="180" ry="90" fill="url(#n7)" />
      </g>
      <g style={{ animation: 'driftZ 26s ease-in-out infinite' }}>
        <ellipse cx="430" cy="90" rx="140" ry="60" fill="url(#n8)" />
      </g>
    </svg>
    <div style={{ zIndex: 10, display:'flex', fontSize:10, fontWeight:700, color:'rgba(216,180,254,0.35)', letterSpacing:'3px' }}>TECHNICAL SKILLS</div>
    <div style={{ zIndex: 10, display:'flex', flexDirection:'column', gap:14 }}>
      {categories.map(function(cat) {
        return (
          <div key={cat.title} style={{ display:'flex', alignItems:'center', gap:16 }}>
            <div style={{ display:'flex', fontSize:10, fontWeight:700, color:cat.color, letterSpacing:'1px', opacity:0.8, width:120 }}>{cat.title.toUpperCase()}</div>
            <div style={{ display:'flex', flexWrap:'wrap', gap:7 }}>
              {cat.items.map(function(item) {
                return (<div key={item} style={{ display:'flex', padding:'4px 13px', borderRadius:6, background:cat.color+'08', border:'1px solid '+cat.color+'22', color:'rgba(244,220,255,0.85)', fontSize:12, fontWeight:600 }}>{item}</div>);
              })}
            </div>
          </div>
        );
      })}
    </div>
    </div>
  );
})()
```

<br>

<!-- GitHub Stats -->
<p align="center">
  <img src="https://raw.githubusercontent.com/nitya747/nitya747/main/.github/assets/streak-stats.svg" alt="Streak Stats" />
</p>

<br>

<div align="center">
  <img src="https://readme-typing-svg.herokuapp.com?font=Inter&weight=500&size=16&duration=4000&pause=1500&color=ec4899&center=true&vCenter=true&width=860&height=30&lines=the+best+way+to+predict+the+future+is+to+invent+it." alt="Quote" />
</div>

<br>

```aura width=120 height=44 link="https://github.com/nitya747" inline align=center
<SocialMediaButton
  icon="https://cdn.jsdelivr.net/npm/simple-icons@v9/icons/github.svg"
  text="GitHub"
  backgroundColor="#140f1a"
  width={120}
  height={44}
  gradientStops={[{ offset: '0%', color: '#ffffff' }, { offset: '100%', color: 'rgba(236,72,153,0.5)' }]}
/>
```

```aura width=140 height=44 link="https://www.linkedin.com/in/nitya-arora-a8a845320" inline align=center
<SocialMediaButton
  icon="https://cdn.jsdelivr.net/npm/simple-icons@v9/icons/linkedin.svg"
  text="LinkedIn"
  backgroundColor="#0f111a"
  width={140}
  height={44}
  gradientStops={[{ offset: '0%', color: '#0077b5' }, { offset: '100%', color: 'rgba(139,92,246,0.5)' }]}
/>
```

```aura width=100 height=44 link="mailto:nityaa7477@gmail.com" inline align=center
<SocialMediaButton
  icon="https://cdn.jsdelivr.net/npm/simple-icons@v9/icons/gmail.svg"
  text="Email"
  backgroundColor="#20141a"
  width={100}
  height={44}
  gradientStops={[{ offset: '0%', color: '#ffffff' }, { offset: '100%', color: 'rgba(236,72,153,0.5)' }]}
/>
```
