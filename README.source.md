```aura width=860 height=200
<div style={{
  width: '100%', height: '100%', background: '#0a0d0a',
  display: 'flex', alignItems: 'center', fontFamily: 'Inter',
  position: 'relative', overflow: 'hidden', borderRadius: 16,
  border: '1px solid rgba(16,185,129,0.18)'
}}>
<style>
{`
  @keyframes drift1 { 0%,100%{transform:translate(0,0)} 50%{transform:translate(30px,-15px)} }
  @keyframes drift2 { 0%,100%{transform:translate(0,0)} 50%{transform:translate(-40px,20px)} }
  @keyframes drift3 { 0%,100%{transform:translate(0,0)} 50%{transform:translate(25px,10px)} }
  @keyframes pulse { 0%,100%{opacity:0.1;transform:scale(0.8)} 50%{opacity:0.8;transform:scale(1.2)} }
  @keyframes flow { 0%{transform:translateX(-20%);opacity:0} 20%{opacity:0.25} 80%{opacity:0.25} 100%{transform:translateX(100%);opacity:0} }
`}
</style>
<svg width="860" height="200" style={{ position: 'absolute', top: 0, left: 0 }}>
  <defs>
    <radialGradient id="n1" cx="50%" cy="50%" r="50%"><stop offset="0%" stopColor="rgba(16,185,129,0.25)" /><stop offset="100%" stopColor="rgba(16,185,129,0)" /></radialGradient>
    <radialGradient id="n2" cx="50%" cy="50%" r="50%"><stop offset="0%" stopColor="rgba(245,158,11,0.2)" /><stop offset="100%" stopColor="rgba(245,158,11,0)" /></radialGradient>
    <radialGradient id="n3" cx="50%" cy="50%" r="50%"><stop offset="0%" stopColor="rgba(255,255,255,0.12)" /><stop offset="100%" stopColor="rgba(255,255,255,0)" /></radialGradient>
  </defs>
  
  <g>
    <circle cx="80" cy="30" r="1.5" fill="#fff" style={{animation: 'pulse 3s infinite'}} />
    <circle cx="250" cy="170" r="2" fill="#fff" style={{animation: 'pulse 4s infinite 1s'}} />
    <circle cx="480" cy="50" r="1.5" fill="#fff" style={{animation: 'pulse 5s infinite 2s'}} />
    <circle cx="720" cy="160" r="1" fill="#fff" style={{animation: 'pulse 3.5s infinite 0.5s'}} />
    <circle cx="820" cy="40" r="2" fill="#fff" style={{animation: 'pulse 4.5s infinite 1.5s'}} />
  </g>

  <g stroke="rgba(255,255,255,0.3)" strokeWidth="1" fill="none">
    <path d="M0,70 Q200,90 400,50 T860,70" style={{animation: 'flow 12s linear infinite'}} />
    <path d="M0,150 Q300,120 500,160 T860,140" style={{animation: 'flow 16s linear infinite 3s'}} />
  </g>

  <g style={{ animation: 'drift1 20s ease-in-out infinite' }}>
    <ellipse cx="160" cy="100" rx="140" ry="70" fill="url(#n1)" />
    <ellipse cx="120" cy="80" rx="90" ry="40" fill="url(#n1)" />
  </g>
  <g style={{ animation: 'drift2 24s ease-in-out infinite' }}>
    <ellipse cx="700" cy="110" rx="150" ry="75" fill="url(#n2)" />
    <ellipse cx="640" cy="90" rx="100" ry="45" fill="url(#n2)" />
  </g>
  <g style={{ animation: 'drift3 18s ease-in-out infinite' }}>
    <ellipse cx="430" cy="40" rx="110" ry="50" fill="url(#n3)" />
  </g>
</svg>

<div style={{
  position: 'absolute', left: 48, top: 52, width: 96, height: 96,
  borderRadius: 48, background: 'linear-gradient(135deg, #10b981, #f59e0b)',
  display: 'flex', alignItems: 'center', justifyContent: 'center',
}}>
  <img src={(github && github.user && github.user.avatarUrl) || 'https://github.githubassets.com/images/modules/logos_page/GitHub-Mark.png'} width={88} height={88} style={{ borderRadius: 44 }} />
</div>

<div style={{ display:'flex', flexDirection:'column', marginLeft:168, gap:8, zIndex: 10 }}>
  <div style={{ display:'flex', fontSize:38, fontWeight:800, color:'#ffffff', letterSpacing:'-1px', lineHeight:1 }}>
    {(github && github.user && (github.user.name || github.user.login)) || 'Nitya Arora'}
  </div>
  <div style={{ display:'flex', fontSize:15, color:'rgba(209,250,229,0.8)', fontWeight:400, letterSpacing:'0.3px' }}>
    {(github && github.user && github.user.bio) || 'Turning Ideas Into Products'}
  </div>
  <div style={{ display:'flex', gap:8, marginTop:6 }}>
    {['Frontend', 'Full Stack', 'Product Builder'].map(function(tag) {
      return (<div key={tag} style={{ display:'flex', padding:'4px 12px', borderRadius:20, background:'rgba(16,185,129,0.1)', border:'1px solid rgba(16,185,129,0.3)', color:'rgba(167,243,208,0.95)', fontSize:12, fontWeight:600 }}>{tag}</div>);
    })}
  </div>
</div>
</div>
```

```aura width=860 height=140
(function() {
  var visitorCount = "{{VISITOR_COUNT}}";
  var stats = [
    { label: 'Repos', value: String((typeof github !== 'undefined' && github.stats && github.stats.totalRepos) || 0), color: '#34d399' },
    { label: 'Stars', value: String((typeof github !== 'undefined' && github.stats && github.stats.totalStars) || 0), color: '#fbbf24' },
    { label: 'Commits', value: String((typeof github !== 'undefined' && github.stats && github.stats.totalCommits) || 0), color: '#f59e0b' },
    { label: 'Visitors', value: String(visitorCount), color: '#10b981' },
  ];
  return (
    <div style={{
      width: '100%', height: '100%', background: '#0a0d0a',
      display: 'flex', alignItems: 'center', justifyContent: 'center',
      fontFamily: 'Inter', borderRadius: 16, border: '1px solid rgba(16,185,129,0.18)',
      position: 'relative', overflow: 'hidden',
    }}>
    <style>{`
      @keyframes driftA { 0%,100%{transform:translate(0,0)} 50%{transform:translate(-30px,15px)} }
      @keyframes driftB { 0%,100%{transform:translate(0,0)} 50%{transform:translate(40px,-10px)} }
      @keyframes pulse { 0%,100%{opacity:0.1;transform:scale(0.8)} 50%{opacity:0.8;transform:scale(1.2)} }
      @keyframes flowFast { 0%{transform:translateX(-10%);opacity:0} 20%{opacity:0.2} 80%{opacity:0.2} 100%{transform:translateX(100%);opacity:0} }
    `}</style>
    <svg width="860" height="140" style={{ position: 'absolute', top: 0, left: 0 }}>
      <defs>
        <radialGradient id="n4" cx="50%" cy="50%" r="50%"><stop offset="0%" stopColor="rgba(245,158,11,0.2)" /><stop offset="100%" stopColor="rgba(245,158,11,0)" /></radialGradient>
        <radialGradient id="n5" cx="50%" cy="50%" r="50%"><stop offset="0%" stopColor="rgba(16,185,129,0.2)" /><stop offset="100%" stopColor="rgba(16,185,129,0)" /></radialGradient>
      </defs>
      
      <g>
        <circle cx="120" cy="20" r="1.5" fill="#fff" style={{animation: 'pulse 3s infinite 0.5s'}} />
        <circle cx="450" cy="110" r="1" fill="#fff" style={{animation: 'pulse 4s infinite 2s'}} />
        <circle cx="780" cy="30" r="2" fill="#fff" style={{animation: 'pulse 5s infinite 1s'}} />
      </g>

      <g stroke="rgba(255,255,255,0.2)" strokeWidth="1" fill="none">
        <path d="M0,40 Q250,70 450,30 T860,60" style={{animation: 'flowFast 10s linear infinite'}} />
      </g>

      <g style={{ animation: 'driftA 18s ease-in-out infinite' }}>
        <ellipse cx="150" cy="70" rx="130" ry="50" fill="url(#n5)" />
      </g>
      <g style={{ animation: 'driftB 22s ease-in-out infinite' }}>
        <ellipse cx="710" cy="70" rx="140" ry="60" fill="url(#n4)" />
      </g>
    </svg>
    {stats.map(function(s, i) {
      return (
        <div key={s.label} style={{ zIndex: 10, flexGrow: 1, display: 'flex', flexDirection: 'column', alignItems: 'center', justifyContent: 'center', padding: '16px 8px', borderRight: i < stats.length - 1 ? '1px solid rgba(255,255,255,0.06)' : 'none', gap: 5 }}>
          <div style={{ display:'flex', fontSize:30, fontWeight:800, color:s.color, lineHeight:1 }}>{s.value}</div>
          <div style={{ display:'flex', fontSize:11, color:'rgba(167,243,208,0.45)', fontWeight:600, letterSpacing:'1.5px' }}>{s.label.toUpperCase()}</div>
        </div>
      );
    })}
    </div>
  );
})()
```

```aura width=860 height=280
(function() {
  var categories = [
    { title: 'Languages', color: '#34d399', items: ['C++', 'Python', 'JavaScript'] },
    { title: 'Frontend', color: '#6ee7b7', items: ['React', 'HTML', 'CSS', 'Tailwind CSS'] },
    { title: 'Backend', color: '#fbbf24', items: ['Node.js', 'Express.js'] },
    { title: 'Database & Infra', color: '#f59e0b', items: ['Supabase', 'Firebase'] },
    { title: 'AI & Tools', color: '#a7f3d0', items: ['OpenAI', 'Git', 'GitHub'] },
  ];
  return (
    <div style={{
      width: '100%', height: '100%', background: '#0a0d0a',
      display: 'flex', flexDirection: 'column', fontFamily: 'Inter', padding: '32px 32px', gap: 18,
      borderRadius: 16, border: '1px solid rgba(16,185,129,0.18)', position: 'relative', overflow: 'hidden',
    }}>
    <style>{`
      @keyframes driftX { 0%,100%{transform:translate(0,0)} 50%{transform:translate(40px,-20px)} }
      @keyframes driftY { 0%,100%{transform:translate(0,0)} 50%{transform:translate(-50px,30px)} }
      @keyframes driftZ { 0%,100%{transform:translate(0,0)} 50%{transform:translate(30px,25px)} }
      @keyframes pulse { 0%,100%{opacity:0.1;transform:scale(0.8)} 50%{opacity:0.8;transform:scale(1.2)} }
      @keyframes flowSlow { 0%{transform:translateX(-10%);opacity:0} 20%{opacity:0.15} 80%{opacity:0.15} 100%{transform:translateX(100%);opacity:0} }
    `}</style>
    <svg width="860" height="280" style={{ position: 'absolute', top: 0, left: 0 }}>
      <defs>
        <radialGradient id="n6" cx="50%" cy="50%" r="50%"><stop offset="0%" stopColor="rgba(16,185,129,0.25)" /><stop offset="100%" stopColor="rgba(16,185,129,0)" /></radialGradient>
        <radialGradient id="n7" cx="50%" cy="50%" r="50%"><stop offset="0%" stopColor="rgba(245,158,11,0.2)" /><stop offset="100%" stopColor="rgba(245,158,11,0)" /></radialGradient>
        <radialGradient id="n8" cx="50%" cy="50%" r="50%"><stop offset="0%" stopColor="rgba(255,255,255,0.08)" /><stop offset="100%" stopColor="rgba(255,255,255,0)" /></radialGradient>
      </defs>

      <g>
        <circle cx="90" cy="50" r="2" fill="#fff" style={{animation: 'pulse 4s infinite'}} />
        <circle cx="320" cy="210" r="1.5" fill="#fff" style={{animation: 'pulse 3s infinite 1s'}} />
        <circle cx="550" cy="80" r="2" fill="#fff" style={{animation: 'pulse 5s infinite 2s'}} />
        <circle cx="780" cy="240" r="1.5" fill="#fff" style={{animation: 'pulse 3.5s infinite 0.5s'}} />
      </g>

      <g stroke="rgba(255,255,255,0.2)" strokeWidth="1" fill="none">
        <path d="M0,100 Q200,130 400,80 T860,110" style={{animation: 'flowSlow 18s linear infinite'}} />
        <path d="M0,220 Q300,190 500,240 T860,210" style={{animation: 'flowSlow 24s linear infinite 5s'}} />
      </g>

      <g style={{ animation: 'driftX 26s ease-in-out infinite' }}>
        <ellipse cx="200" cy="180" rx="160" ry="80" fill="url(#n6)" />
      </g>
      <g style={{ animation: 'driftY 30s ease-in-out infinite' }}>
        <ellipse cx="680" cy="200" rx="180" ry="90" fill="url(#n7)" />
      </g>
      <g style={{ animation: 'driftZ 22s ease-in-out infinite' }}>
        <ellipse cx="430" cy="90" rx="140" ry="60" fill="url(#n8)" />
      </g>
    </svg>
    <div style={{ zIndex: 10, display:'flex', fontSize:10, fontWeight:700, color:'rgba(167,243,208,0.5)', letterSpacing:'3px' }}>TECHNICAL SKILLS</div>
    <div style={{ zIndex: 10, display:'flex', flexDirection:'column', gap:14 }}>
      {categories.map(function(cat) {
        return (
          <div key={cat.title} style={{ display:'flex', alignItems:'center', gap:16 }}>
            <div style={{ display:'flex', fontSize:10, fontWeight:700, color:cat.color, letterSpacing:'1px', width:120 }}>{cat.title.toUpperCase()}</div>
            <div style={{ display:'flex', flexWrap:'wrap', gap:7 }}>
              {cat.items.map(function(item) {
                return (<div key={item} style={{ display:'flex', padding:'4px 13px', borderRadius:6, background:cat.color+'15', border:'1px solid '+cat.color+'35', color:'rgba(225,255,255,0.85)', fontSize:12, fontWeight:600 }}>{item}</div>);
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
  <img src="https://streak-stats.demolab.com?user=nitya747&theme=dark&hide_border=true" alt="Streak Stats" />
</p>

<br>

<div align="center">
  <img src="https://readme-typing-svg.herokuapp.com?font=Inter&weight=500&size=16&duration=4000&pause=1500&color=10b981&center=true&vCenter=true&width=860&height=30&lines=the+best+way+to+predict+the+future+is+to+invent+it." alt="Quote" />
</div>

<br>

```aura width=120 height=44 link="https://github.com/nitya747" inline align=center
<SocialMediaButton
  icon="https://cdn.jsdelivr.net/npm/simple-icons@v9/icons/github.svg"
  text="GitHub"
  backgroundColor="#111511"
  width={120}
  height={44}
  gradientStops={[{ offset: '0%', color: '#ffffff' }, { offset: '100%', color: '#34d399' }]}
/>
```

```aura width=140 height=44 link="https://www.linkedin.com/in/nitya-arora-a8a845320" inline align=center
<SocialMediaButton
  icon="https://cdn.jsdelivr.net/npm/simple-icons@v9/icons/linkedin.svg"
  text="LinkedIn"
  backgroundColor="#071b15"
  width={140}
  height={44}
  gradientStops={[{ offset: '0%', color: '#0077b5' }, { offset: '100%', color: '#10b981' }]}
/>
```

```aura width=100 height=44 link="mailto:nityaa7477@gmail.com" inline align=center
<SocialMediaButton
  icon="https://cdn.jsdelivr.net/npm/simple-icons@v9/icons/gmail.svg"
  text="Email"
  backgroundColor="#2b1a0a"
  width={100}
  height={44}
  gradientStops={[{ offset: '0%', color: '#ffffff' }, { offset: '100%', color: '#EA4335' }]}
/>
```
