<!doctype html><html><head><meta charset=utf8><meta name=viewport content="width=device-width,initial-scale=1,viewport-fit=cover"><style>:root{color-scheme:light;box-sizing:border-box;padding-top:env(safe-area-inset-top,0px);padding-bottom:env(safe-area-inset-bottom,0px)}html{scroll-padding-top:env(safe-area-inset-top,0px)}body{margin:0;padding:0;font:14px -apple-system,BlinkMacSystemFont,sans-serif;background:#fff;color:#000}img{max-width:100%}[hidden]:not([hidden=until-found i]){display:none!important}</style></head><body>
<title>MiniNet Routing Lab</title>
<meta name="claude:viewport-fit-sides" content="cover">
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Chakra+Petch:wght@500;700&family=IBM+Plex+Mono:wght@400;500&family=IBM+Plex+Sans:wght@400;500;600&display=swap" rel="stylesheet">
<style>
/* Layout: 3D topology stage on the left with link controls and the BFS trace under it; queue, stats and linked-list log stacked on the right. Single dark look by choice, like a network operations screen. */
:root {
  --bg: #070b14;
  --panel: #0d1524;
  --panel2: #111c30;
  --line: #1d2b45;
  --fg: #d9e4f5;
  --muted: #8196b6;
  --cyan: #3dd6d0;
  --amber: #f5b942;
  --green: #5ee08a;
  --red: #ff6275;
  --indigo: #8591ff;
  --display: 'Chakra Petch', system-ui, sans-serif;
  --body: 'IBM Plex Sans', system-ui, sans-serif;
  --mono: 'IBM Plex Mono', ui-monospace, Menlo, monospace;
  color-scheme: dark;
}
* { box-sizing: border-box; }
body {
  background: var(--bg);
  color: var(--fg);
  font-family: var(--body);
  font-size: 14px;
  line-height: 1.5;
  padding-block: 24px 44px;
  padding-left: max(16px, env(safe-area-inset-left, 0px));
  padding-right: max(16px, env(safe-area-inset-right, 0px));
}
.wrap { max-width: 1180px; margin: 0 auto; }
header h1 {
  font-family: var(--display);
  font-weight: 700;
  font-size: clamp(24px, 4vw, 34px);
  letter-spacing: 0.01em;
  margin: 0;
  text-wrap: balance;
}
header h1 span { color: var(--cyan); }
header p { margin: 8px 0 0; color: var(--muted); max-width: 64ch; }
.grid {
  display: grid;
  grid-template-columns: minmax(0, 1.75fr) minmax(0, 1fr);
  gap: 16px;
  margin-top: 20px;
  align-items: start;
}
.col { display: flex; flex-direction: column; gap: 16px; min-width: 0; }
@media (max-width: 900px) { .grid { grid-template-columns: minmax(0, 1fr); } }
.card {
  background: var(--panel);
  border: 1px solid var(--line);
  border-radius: 10px;
  padding: 14px;
  min-width: 0;
}
.card h2 {
  font: 500 11px var(--mono);
  letter-spacing: 0.14em;
  text-transform: uppercase;
  color: var(--muted);
  margin: 0 0 10px;
  display: flex;
  justify-content: space-between;
  gap: 8px;
  flex-wrap: wrap;
}
.toolbar { display: flex; flex-wrap: wrap; gap: 10px; align-items: flex-end; margin-bottom: 12px; }
.field { display: flex; flex-direction: column; gap: 4px; }
.field label { font: 500 10px var(--mono); letter-spacing: 0.12em; text-transform: uppercase; color: var(--muted); }
select, button { font: inherit; color: inherit; }
select {
  background: var(--panel2);
  border: 1px solid var(--line);
  border-radius: 6px;
  padding: 7px 10px;
  min-width: 140px;
}
button {
  background: var(--panel2);
  border: 1px solid var(--line);
  border-radius: 6px;
  padding: 7px 12px;
  cursor: pointer;
}
button:hover { border-color: #34496f; }
button.primary { background: var(--cyan); color: #04201f; border-color: var(--cyan); font-weight: 600; }
button.primary:hover { filter: brightness(1.08); }
:focus-visible { outline: 2px solid var(--cyan); outline-offset: 2px; }
.stage {
  position: relative;
  border-radius: 8px;
  overflow: hidden;
  border: 1px solid var(--line);
  background: radial-gradient(ellipse at 50% 42%, #112140 0%, #070b14 72%);
}
canvas { display: block; width: 100%; touch-action: pan-y; cursor: grab; }
.hud { position: absolute; left: 12px; right: 12px; top: 10px; pointer-events: none; }
.hud-route { font: 500 clamp(14px, 2.6vw, 18px) var(--mono); color: var(--fg); }
.hud-sub { font: 400 12px var(--mono); color: var(--muted); margin-top: 2px; }
.legend {
  position: absolute;
  left: 12px;
  right: 12px;
  bottom: 10px;
  display: flex;
  flex-wrap: wrap;
  gap: 4px 14px;
  font: 400 11px var(--mono);
  color: var(--muted);
  pointer-events: none;
}
.legend i { display: inline-block; width: 9px; height: 9px; border-radius: 50%; margin-right: 5px; vertical-align: -1px; }
.hint { color: var(--muted); font-size: 12px; margin: 8px 0 0; }
.links { display: flex; flex-wrap: wrap; gap: 8px; }
.chip { display: inline-flex; align-items: center; gap: 8px; font-family: var(--mono); font-size: 12px; }
.chip .dot { width: 8px; height: 8px; border-radius: 50%; background: var(--green); }
.chip[aria-pressed="true"] { border-color: var(--red); color: var(--red); }
.chip[aria-pressed="true"] .dot { background: var(--red); }
.chip small { color: var(--muted); font-size: 11px; }
.trace { display: flex; flex-direction: column; gap: 4px; max-height: 270px; overflow: auto; }
.row {
  display: grid;
  grid-template-columns: 26px minmax(0, 1fr);
  gap: 8px;
  padding: 6px 8px;
  border-radius: 6px;
  background: var(--panel2);
  font: 400 12px var(--mono);
  align-items: start;
}
.row.cur { outline: 1px solid var(--amber); }
.row.done { outline: 1px solid var(--green); }
.row.fail { outline: 1px solid var(--red); }
.row .n { color: var(--muted); }
.row .body { display: flex; flex-wrap: wrap; gap: 4px 10px; align-items: center; min-width: 0; }
.row .lbl { color: var(--muted); }
.nchip {
  display: inline-block;
  padding: 0 6px;
  border-radius: 4px;
  border: 1px solid var(--line);
  background: var(--bg);
  font: 500 11px var(--mono);
}
.nchip.g { border-color: var(--green); color: var(--green); }
.empty { color: var(--muted); font-size: 12px; padding: 10px; border: 1px dashed var(--line); border-radius: 6px; }
.stats { display: grid; grid-template-columns: repeat(auto-fit, minmax(92px, 1fr)); gap: 8px; }
.stat { background: var(--panel2); border-radius: 6px; padding: 8px 10px; }
.stat b { display: block; font: 500 22px var(--mono); font-variant-numeric: tabular-nums; }
.stat span { font-size: 11px; color: var(--muted); }
.qrow {
  display: grid;
  grid-template-columns: auto 1fr auto;
  gap: 10px;
  align-items: center;
  padding: 7px 10px;
  background: var(--panel2);
  border-radius: 6px;
  font: 400 12px var(--mono);
}
.q { display: flex; flex-direction: column; gap: 4px; }
.pill { padding: 1px 8px; border-radius: 99px; font: 500 10px var(--mono); letter-spacing: 0.08em; border: 1px solid; }
.pill.waiting { color: var(--muted); border-color: var(--line); }
.pill.routing { color: var(--amber); border-color: var(--amber); }
.pill.delivered { color: var(--green); border-color: var(--green); }
.pill.failed { color: var(--red); border-color: var(--red); }
.chain { display: flex; align-items: stretch; overflow-x: auto; padding: 2px 0 8px; font: 400 11px var(--mono); }
.chain > * { flex: none; }
.tag { align-self: center; color: var(--muted); padding: 0 6px; }
.arrow { align-self: center; color: var(--muted); padding: 0 4px; }
.lnode { background: var(--panel2); border: 1px solid var(--line); border-radius: 6px; padding: 6px 9px; min-width: 96px; }
.lnode b { display: block; font-weight: 500; }
.lnode.delivered { border-color: #2c6b45; }
.lnode.failed { border-color: #7a2f3a; }
.foot { color: var(--muted); font-size: 12px; margin: 10px 0 0; }
.nogl { display: none; padding: 40px 16px; text-align: center; color: var(--muted); }
</style>

<div class="wrap">
  <header>
    <h1>MiniNet <span>Routing Lab</span></h1>
    <p>Drag the network to rotate it. Send a message to watch the queue hand it to BFS, then break a link to see the route change. It opens with one sample message (#1042) already delivered.</p>
  </header>

  <div class="grid">
    <div class="col">
      <section class="card" aria-label="3D network topology">
        <h2><span>Topology · 6 nodes · 7 links</span><span id="spinState">auto-rotate on</span></h2>
        <div class="toolbar">
          <div class="field"><label for="src">From</label><select id="src"></select></div>
          <div class="field"><label for="dst">To</label><select id="dst"></select></div>
          <button class="primary" id="send" type="button">Send message</button>
          <button id="spin" type="button">Pause spin</button>
          <button id="resetView" type="button">Reset view</button>
        </div>
        <div class="stage" id="stage">
          <canvas id="cv" aria-label="Rotatable 3D view of the network graph"></canvas>
          <div class="nogl" id="nogl">The 3D view needs WebGL, which this browser is not providing. The queue, trace and log below still work.</div>
          <div class="hud" aria-live="polite"><div class="hud-route" id="hudRoute"></div><div class="hud-sub" id="hudSub"></div></div>
          <div class="legend">
            <span><i style="background:#3dd6d0"></i>client</span>
            <span><i style="background:#3b5385"></i>router</span>
            <span><i style="background:#8591ff"></i>in BFS queue</span>
            <span><i style="background:#f5b942"></i>visited</span>
            <span><i style="background:#5ee08a"></i>route</span>
            <span><i style="background:#ff6275"></i>link down</span>
          </div>
        </div>
      </section>

      <section class="card" aria-label="Link controls">
        <h2><span>Links</span><span>toggle to simulate a failure</span></h2>
        <div class="links" id="links"></div>
        <p class="hint">Breaking a link on the current route re-runs BFS right away and shows the alternative path.</p>
        <div style="margin-top:10px"><button id="reset" type="button">Restore all links</button></div>
      </section>

      <section class="card" aria-label="BFS trace">
        <h2><span>BFS trace</span><span id="traceMeta"></span></h2>
        <div class="trace" id="trace"></div>
        <p class="foot">BFS visits every node and link at most once, so it runs in O(V + E). Queue and Stack operations are O(1).</p>
      </section>
    </div>

    <div class="col">
      <section class="card" aria-label="Statistics">
        <h2><span>Network statistics</span></h2>
        <div class="stats" id="stats"></div>
      </section>

      <section class="card" aria-label="Message queue">
        <h2><span>Message queue · FIFO</span><span>front → back</span></h2>
        <div class="q" id="queue"></div>
      </section>

      <section class="card" aria-label="Message log">
        <h2><span>Message log · linked list</span><span id="logSize"></span></h2>
        <div class="chain" id="log"></div>
      </section>
    </div>
  </div>
</div>

<script src="https://cdnjs.cloudflare.com/ajax/libs/three.js/r128/three.min.js"></script>
<script>
(function () {
  'use strict';

  /* ---------- Own data structures (the DSA part) ---------- */
  class QNode { constructor(v) { this.v = v; this.next = null; } }
  class LinkedQueue {
    constructor() { this.head = null; this.tail = null; this.size = 0; }
    enqueue(v) { const n = new QNode(v); if (this.tail) this.tail.next = n; else this.head = n; this.tail = n; this.size++; }
    dequeue() {
      if (!this.head) return undefined;
      const v = this.head.v; this.head = this.head.next;
      if (!this.head) this.tail = null;
      this.size--; return v;
    }
    isEmpty() { return this.size === 0; }
    toArray() { const a = []; for (let n = this.head; n; n = n.next) a.push(n.v); return a; }
  }
  class LinkedList {
    constructor() { this.head = null; this.tail = null; this.size = 0; }
    append(v) { const n = new QNode(v); if (this.tail) this.tail.next = n; else this.head = n; this.tail = n; this.size++; }
    toArray() { const a = []; for (let n = this.head; n; n = n.next) a.push(n.v); return a; }
  }
  class Stack {
    constructor() { this.a = []; }
    push(v) { this.a.push(v); }
    pop() { return this.a.pop(); }
    isEmpty() { return this.a.length === 0; }
  }

  /* ---------- Topology ---------- */
  const NODES = [
    { name: 'Naiha',  client: true,  pos: [-4.4, 0, 0] },
    { name: 'router', client: false, pos: [-1.6, 2.1, 1.6] },
    { name: 'router', client: false, pos: [-1.6, -1.9, -1.6] },
    { name: 'router', client: false, pos: [1.6, 1.9, -1.2] },
    { name: 'router', client: false, pos: [1.6, -2.0, 1.6] },
    { name: 'Ayesha', client: true,  pos: [4.4, 0, 0] }
  ];
  const EDGES = [[0, 1], [0, 2], [1, 3], [2, 3], [2, 4], [3, 5], [4, 5]];
  const down = new Set();
  const key = (a, b) => (a < b ? a + '-' + b : b + '-' + a);
  const nm = i => 'N' + (i + 1);
  const linkName = (a, b) => nm(a) + '–' + nm(b);

  function neighbors(n) {
    const out = [];
    for (const [a, b] of EDGES) {
      if (down.has(key(a, b))) continue;
      if (a === n) out.push(b); else if (b === n) out.push(a);
    }
    return out;
  }

  function bfs(src, dst) {
    const q = new LinkedQueue();
    const visited = new Set([src]);
    const parent = new Map();
    const steps = [];
    q.enqueue(src);
    while (!q.isEmpty()) {
      const cur = q.dequeue();
      steps.push({ cur: cur, queue: q.toArray(), found: cur === dst });
      if (cur === dst) {
        const st = new Stack();
        let n = dst;
        while (n !== undefined) { st.push(n); n = parent.get(n); }
        const path = [];
        while (!st.isEmpty()) path.push(st.pop());
        return { steps: steps, path: path };
      }
      for (const nb of neighbors(cur)) {
        if (!visited.has(nb)) { visited.add(nb); parent.set(nb, cur); q.enqueue(nb); }
      }
    }
    return { steps: steps, path: null };
  }

  /* ---------- App state ---------- */
  const RM = window.matchMedia && matchMedia('(prefers-reduced-motion: reduce)').matches;
  const sleep = ms => new Promise(r => setTimeout(r, RM ? ms * 0.3 : ms));
  const $ = id => document.getElementById(id);

  const pending = new LinkedQueue();
  const log = new LinkedList();
  const stats = { sent: 0, delivered: 0, failed: 0, lat: [], hops: 0 };
  let active = null, busy = false, nextId = 1042;
  let lastSrc = 0, lastDst = 5;
  let routeEdges = new Set();
  const nodeState = NODES.map(() => 'idle');

  /* ---------- Three.js scene ---------- */
  const cv = $('cv'), stage = $('stage');
  let gl = false, renderer, scene, camera, world, packet, spin = true, dragging = false;
  const nodeMeshes = [], rings = [], edgeMeshes = {}, edgeMarks = {};
  const COL = { queued: 0x8591ff, done: 0xf5b942, cur: 0xffffff, path: 0x5ee08a, fail: 0xff6275 };

  function makeLabel(i) {
    const c = document.createElement('canvas'); c.width = 256; c.height = 112;
    const ctx = c.getContext('2d');
    const tex = new THREE.CanvasTexture(c);
    const draw = function () {
      ctx.clearRect(0, 0, 256, 112);
      ctx.textAlign = 'center';
      ctx.fillStyle = '#d9e4f5'; ctx.font = '700 46px "Chakra Petch", sans-serif';
      ctx.fillText(nm(i), 128, 50);
      ctx.fillStyle = '#8196b6'; ctx.font = '400 24px "IBM Plex Mono", monospace';
      ctx.fillText(NODES[i].name, 128, 88);
      tex.needsUpdate = true;
    };
    draw();
    if (document.fonts && document.fonts.ready) document.fonts.ready.then(draw);
    const sp = new THREE.Sprite(new THREE.SpriteMaterial({ map: tex, transparent: true, depthTest: false }));
    sp.scale.set(2.2, 0.96, 1);
    return sp;
  }

  function makeEdge(a, b) {
    const A = new THREE.Vector3(...NODES[a].pos), B = new THREE.Vector3(...NODES[b].pos);
    const d = B.clone().sub(A), len = d.length();
    const m = new THREE.Mesh(
      new THREE.CylinderGeometry(0.045, 0.045, len, 8),
      new THREE.MeshBasicMaterial({ color: 0x3a5385, transparent: true, opacity: 0.9 })
    );
    m.position.copy(A.clone().add(B).multiplyScalar(0.5));
    m.quaternion.setFromUnitVectors(new THREE.Vector3(0, 1, 0), d.normalize());
    return m;
  }

  function initGL() {
    if (typeof THREE === 'undefined') return;
    try { renderer = new THREE.WebGLRenderer({ canvas: cv, antialias: true }); } catch (e) { return; }
    renderer.setPixelRatio(Math.min(window.devicePixelRatio || 1, 2));
    renderer.setClearColor(0x070b14, 1);
    scene = new THREE.Scene();
    scene.fog = new THREE.Fog(0x070b14, 14, 28);
    camera = new THREE.PerspectiveCamera(42, 1, 0.1, 100);
    camera.position.set(0, 1.2, 12.5);
    camera.lookAt(0, 0, 0);
    scene.add(new THREE.AmbientLight(0x8899bb, 0.75));
    const p1 = new THREE.PointLight(0xffffff, 1.1); p1.position.set(6, 8, 8); scene.add(p1);
    const p2 = new THREE.PointLight(0x3dd6d0, 0.7); p2.position.set(-8, -4, -6); scene.add(p2);
    world = new THREE.Group(); world.rotation.y = -0.5; world.rotation.x = 0.18; scene.add(world);

    const grid = new THREE.GridHelper(18, 18, 0x1d2b45, 0x13203a);
    grid.position.y = -3.4; world.add(grid);

    const pts = new Float32Array(220 * 3);
    for (let i = 0; i < 220; i++) {
      const r = 8 + Math.random() * 6, th = Math.random() * 6.283, ph = Math.acos(2 * Math.random() - 1);
      pts[i * 3] = r * Math.sin(ph) * Math.cos(th); pts[i * 3 + 1] = r * Math.cos(ph); pts[i * 3 + 2] = r * Math.sin(ph) * Math.sin(th);
    }
    const sg = new THREE.BufferGeometry(); sg.setAttribute('position', new THREE.BufferAttribute(pts, 3));
    world.add(new THREE.Points(sg, new THREE.PointsMaterial({ color: 0x4a6aa0, size: 0.05 })));

    EDGES.forEach(function (e) {
      const k = key(e[0], e[1]);
      const m = makeEdge(e[0], e[1]); world.add(m); edgeMeshes[k] = m;
      const mark = new THREE.Mesh(new THREE.OctahedronGeometry(0.2), new THREE.MeshBasicMaterial({ color: 0xff6275 }));
      mark.position.copy(m.position); mark.visible = false; world.add(mark); edgeMarks[k] = mark;
    });

    NODES.forEach(function (n, i) {
      const r = n.client ? 0.5 : 0.36;
      const m = new THREE.Mesh(new THREE.SphereGeometry(r, 32, 24), new THREE.MeshStandardMaterial({ roughness: 0.35, metalness: 0.2 }));
      m.position.set(...n.pos); world.add(m); nodeMeshes.push(m);
      if (n.client) {
        const ring = new THREE.Mesh(new THREE.TorusGeometry(r + 0.24, 0.025, 8, 56), new THREE.MeshBasicMaterial({ color: 0x3dd6d0 }));
        ring.position.copy(m.position); ring.rotation.x = Math.PI / 2; world.add(ring); rings.push(ring);
      }
      const lb = makeLabel(i); lb.position.set(n.pos[0], n.pos[1] + r + 0.85, n.pos[2]); world.add(lb);
    });

    packet = new THREE.Group();
    packet.add(new THREE.Mesh(new THREE.SphereGeometry(0.16, 16, 12), new THREE.MeshBasicMaterial({ color: 0xffffff })));
    packet.add(new THREE.Mesh(new THREE.SphereGeometry(0.34, 16, 12), new THREE.MeshBasicMaterial({ color: 0xf5b942, transparent: true, opacity: 0.28 })));
    packet.visible = false; world.add(packet);

    cv.addEventListener('pointerdown', function (e) {
      dragging = true; lx = e.clientX; ly = e.clientY;
      try { cv.setPointerCapture(e.pointerId); } catch (_) {}
      cv.style.cursor = 'grabbing';
    });
    cv.addEventListener('pointermove', function (e) {
      if (!dragging) return;
      world.rotation.y += (e.clientX - lx) * 0.008;
      world.rotation.x = Math.max(-0.9, Math.min(0.9, world.rotation.x + (e.clientY - ly) * 0.006));
      lx = e.clientX; ly = e.clientY;
    });
    const end = function () { dragging = false; cv.style.cursor = 'grab'; };
    cv.addEventListener('pointerup', end);
    cv.addEventListener('pointercancel', end);
    gl = true;
  }
  let lx = 0, ly = 0;

  function resize() {
    const w = stage.clientWidth || 600, h = w < 560 ? 340 : 460;
    cv.style.height = h + 'px';
    if (!gl) return;
    renderer.setSize(w, h, false);
    camera.aspect = w / h;
    camera.position.z = w < 560 ? 16 : 12.5;
    camera.updateProjectionMatrix();
  }

  function loop(now) {
    requestAnimationFrame(loop);
    if (!gl) return;
    if (spin && !dragging && !RM) world.rotation.y += 0.0024;
    rings.forEach(function (r) { r.rotation.z += 0.01; });
    nodeMeshes.forEach(function (m, i) {
      const s = nodeState[i] === 'cur' ? 1 + 0.16 * Math.sin(now / 110) : 1;
      m.scale.setScalar(s);
    });
    Object.keys(edgeMarks).forEach(function (k) { edgeMarks[k].rotation.y += 0.04; });
    renderer.render(scene, camera);
  }

  function applyNodes() {
    if (!gl) return;
    nodeMeshes.forEach(function (m, i) {
      const st = nodeState[i];
      const c = COL[st] !== undefined ? COL[st] : (NODES[i].client ? 0x1fb5b0 : 0x3b5385);
      m.material.color.setHex(c);
      m.material.emissive.setHex(c);
      m.material.emissiveIntensity = st === 'idle' ? 0.28 : (st === 'cur' ? 0.95 : 0.6);
    });
  }

  function applyEdges() {
    if (!gl) return;
    EDGES.forEach(function (e) {
      const k = key(e[0], e[1]), m = edgeMeshes[k], mk = edgeMarks[k];
      if (down.has(k)) {
        m.material.color.setHex(0xff6275); m.material.opacity = 0.3; m.scale.set(0.6, 1, 0.6); mk.visible = true;
      } else if (routeEdges.has(k)) {
        m.material.color.setHex(0x5ee08a); m.material.opacity = 1; m.scale.set(2.6, 1, 2.6); mk.visible = false;
      } else {
        m.material.color.setHex(0x3a5385); m.material.opacity = 0.9; m.scale.set(1, 1, 1); mk.visible = false;
      }
    });
  }

  function travel(path) {
    return new Promise(function (res) {
      if (!gl) { res(); return; }
      let seg = 0, t0 = performance.now();
      const dur = RM ? 200 : 750;
      packet.visible = true;
      function step(now) {
        const t = Math.min(1, (now - t0) / dur);
        const a = nodeMeshes[path[seg]].position, b = nodeMeshes[path[seg + 1]].position;
        const e = t < 0.5 ? 2 * t * t : 1 - Math.pow(-2 * t + 2, 2) / 2;
        packet.position.lerpVectors(a, b, e);
        if (t >= 1) {
          seg++; t0 = now;
          if (seg >= path.length - 1) { packet.visible = false; res(); return; }
        }
        requestAnimationFrame(step);
      }
      requestAnimationFrame(step);
    });
  }

  /* ---------- Rendering of the panels ---------- */
  const chip = (i, cls) => '<span class="nchip ' + (cls || '') + '">' + nm(i) + '</span>';
  const chips = arr => arr.length ? arr.map(i => chip(i)).join('') : '<span class="lbl">empty</span>';

  function setHud(route, sub) { $('hudRoute').textContent = route; $('hudSub').textContent = sub; }

  function renderTrace(steps, upto, path) {
    let h = '';
    for (let i = 0; i < upto; i++) {
      const s = steps[i];
      h += '<div class="row' + (i === upto - 1 && !path ? ' cur' : '') + '"><span class="n">' + (i + 1) + '</span><span class="body"><span><span class="lbl">dequeue</span> ' + chip(s.cur) + '</span><span><span class="lbl">queue</span> ' + chips(s.queue) + '</span></span></div>';
    }
    const complete = upto === steps.length;
    const last = steps[steps.length - 1];
    if (complete && path) {
      h += '<div class="row done"><span class="n">✓</span><span class="body"><span class="lbl">Stack pops the path</span>' + path.map(i => chip(i, 'g')).join('<span class="lbl">→</span>') + '</span></div>';
    } else if (complete && !path) {
      h += '<div class="row fail"><span class="n">✕</span><span class="body"><span class="lbl">Queue emptied before reaching the destination. No route.</span></span></div>';
    }
    $('trace').innerHTML = h || '<div class="empty">No steps yet.</div>';
    $('trace').scrollTop = $('trace').scrollHeight;
    $('traceMeta').textContent = steps.length ? steps.length + ' dequeues' : '';
  }

  function renderQueue() {
    const items = [];
    if (active) items.push(active);
    pending.toArray().forEach(t => items.push(t));
    if (!items.length) { $('queue').innerHTML = '<div class="empty">Queue is empty. Press Send message to add a task.</div>'; return; }
    $('queue').innerHTML = items.map(function (t) {
      const cls = t.status.toLowerCase();
      return '<div class="qrow"><span>#' + t.id + '</span><span>' + nm(t.src) + ' → ' + nm(t.dst) + '</span><span class="pill ' + cls + '">' + t.status + '</span></div>';
    }).join('');
  }

  function renderLog() {
    const all = log.toArray(), shown = all.slice(-6);
    let h = '<span class="tag">HEAD</span><span class="arrow">→</span>';
    if (all.length > shown.length) h += '<span class="tag">… ' + (all.length - shown.length) + ' older</span><span class="arrow">→</span>';
    shown.forEach(function (e) {
      h += '<div class="lnode ' + e.status.toLowerCase() + '"><b>#' + e.id + '</b>' + nm(e.src) + ' → ' + nm(e.dst) + '<br>' + e.status.toLowerCase() + (e.ms ? ' · ' + e.ms + ' ms' : '') + '</div><span class="arrow">→</span>';
    });
    h += '<span class="tag">NULL</span>';
    $('log').innerHTML = h;
    $('logSize').textContent = all.length + (all.length === 1 ? ' node' : ' nodes');
  }

  function renderStats() {
    const avg = stats.lat.length ? Math.round(stats.lat.reduce((a, b) => a + b, 0) / stats.lat.length) : 0;
    const cells = [['Sent', stats.sent], ['Delivered', stats.delivered], ['Failed', stats.failed], ['Avg latency', avg + ' ms'], ['Last route', stats.hops + ' hops']];
    $('stats').innerHTML = cells.map(c => '<div class="stat"><b>' + c[1] + '</b><span>' + c[0] + '</span></div>').join('');
  }

  function renderLinks() {
    $('links').innerHTML = EDGES.map(function (e) {
      const k = key(e[0], e[1]), isDown = down.has(k);
      return '<button type="button" class="chip" data-k="' + k + '" aria-pressed="' + isDown + '"><span class="dot"></span>' + linkName(e[0], e[1]) + ' <small>' + (isDown ? 'down' : 'up') + '</small></button>';
    }).join('');
  }

  /* ---------- Scene state helpers ---------- */
  function showStep(steps, i) {
    for (let k = 0; k < nodeState.length; k++) nodeState[k] = 'idle';
    for (let k = 0; k < i; k++) nodeState[steps[k].cur] = 'done';
    steps[i].queue.forEach(n => { nodeState[n] = 'queued'; });
    nodeState[steps[i].cur] = 'cur';
    applyNodes();
    setHud('BFS · dequeue ' + nm(steps[i].cur), 'queue: ' + (steps[i].queue.length ? steps[i].queue.map(nm).join(', ') : 'empty'));
  }

  function showRoute(path, note) {
    for (let k = 0; k < nodeState.length; k++) nodeState[k] = 'idle';
    path.forEach(n => { nodeState[n] = 'path'; });
    routeEdges = new Set();
    for (let i = 0; i < path.length - 1; i++) routeEdges.add(key(path[i], path[i + 1]));
    applyNodes(); applyEdges();
    setHud(path.map(nm).join(' → '), (note ? note + ' ' : '') + (path.length - 1) + ' hops');
  }

  function showFinal(src, dst, note) {
    lastSrc = src; lastDst = dst;
    const r = bfs(src, dst);
    renderTrace(r.steps, r.steps.length, r.path);
    if (r.path) { showRoute(r.path, note); stats.hops = r.path.length - 1; }
    else {
      for (let k = 0; k < nodeState.length; k++) nodeState[k] = 'idle';
      nodeState[src] = 'fail'; nodeState[dst] = 'fail';
      routeEdges = new Set(); applyNodes(); applyEdges();
      setHud('No route ' + nm(src) + ' → ' + nm(dst), (note ? note + ' ' : '') + 'every path is down');
    }
    renderStats();
    return r;
  }

  /* ---------- Message processing ---------- */
  async function run(t) {
    t.status = 'ROUTING'; renderQueue();
    lastSrc = t.src; lastDst = t.dst;
    const r = bfs(t.src, t.dst);
    routeEdges = new Set(); applyEdges();
    for (let i = 0; i < r.steps.length; i++) {
      showStep(r.steps, i);
      renderTrace(r.steps, i + 1, null);
      await sleep(620);
    }
    let ms = 0;
    if (!r.path) {
      t.status = 'FAILED'; stats.failed++;
      renderTrace(r.steps, r.steps.length, null);
      for (let k = 0; k < nodeState.length; k++) nodeState[k] = 'idle';
      nodeState[t.src] = 'fail'; nodeState[t.dst] = 'fail';
      applyNodes();
      setHud('No route ' + nm(t.src) + ' → ' + nm(t.dst), 'message #' + t.id + ' failed');
      await sleep(600);
    } else {
      renderTrace(r.steps, r.steps.length, r.path);
      showRoute(r.path, 'message #' + t.id + ' routing.');
      await sleep(250);
      await travel(r.path);
      t.status = 'DELIVERED'; stats.delivered++;
      ms = (r.path.length - 1) * 4 + 5 + Math.floor(Math.random() * 6);
      stats.lat.push(ms); stats.hops = r.path.length - 1;
      setHud(r.path.map(nm).join(' → '), 'message #' + t.id + ' delivered in ' + ms + ' ms');
    }
    log.append({ id: t.id, src: t.src, dst: t.dst, status: t.status, ms: ms });
    renderLog(); renderStats();
  }

  async function pump() {
    if (busy) return;
    busy = true;
    while (!pending.isEmpty()) {
      active = pending.dequeue();
      await run(active);
      active = null; renderQueue();
    }
    busy = false;
  }

  function send() {
    const src = +$('src').value, dst = +$('dst').value;
    if (src === dst) { setHud('Pick two different nodes', 'From and To must not be the same.'); return; }
    nextId++;
    pending.enqueue({ id: nextId, src: src, dst: dst, status: 'WAITING' });
    stats.sent++;
    renderQueue(); renderStats();
    pump();
  }

  /* ---------- Wiring ---------- */
  function init() {
    const opts = NODES.map((n, i) => '<option value="' + i + '">' + nm(i) + ' · ' + n.name + '</option>').join('');
    $('src').innerHTML = opts; $('dst').innerHTML = opts;
    $('src').value = '0'; $('dst').value = '5';

    initGL();
    if (!gl) { cv.style.display = 'none'; $('nogl').style.display = 'block'; }
    resize();
    if (window.ResizeObserver) new ResizeObserver(resize).observe(stage); else window.addEventListener('resize', resize);

    renderLinks();
    // Sample state: message #1042 already delivered over the shortest route.
    stats.sent = 1; stats.delivered = 1; stats.lat.push(14);
    log.append({ id: 1042, src: 0, dst: 5, status: 'DELIVERED', ms: 14 });
    showFinal(0, 5, 'sample message #1042.');
    renderQueue(); renderLog(); renderStats();

    $('send').addEventListener('click', send);
    $('spin').addEventListener('click', function () {
      spin = !spin;
      $('spin').textContent = spin ? 'Pause spin' : 'Resume spin';
      $('spinState').textContent = spin ? 'auto-rotate on' : 'auto-rotate off';
    });
    $('resetView').addEventListener('click', function () { if (gl) { world.rotation.set(0.18, -0.5, 0); } });
    $('links').addEventListener('click', function (e) {
      const b = e.target.closest('button[data-k]'); if (!b) return;
      const k = b.getAttribute('data-k');
      const wasDown = down.has(k);
      if (wasDown) down.delete(k); else down.add(k);
      renderLinks(); applyEdges();
      const nice = k.split('-').map(n => 'N' + (+n + 1)).join('–');
      if (!busy) showFinal(lastSrc, lastDst, nice + (wasDown ? ' restored.' : ' is down, BFS rerouted.'));
    });
    $('reset').addEventListener('click', function () {
      down.clear(); renderLinks(); applyEdges();
      if (!busy) showFinal(lastSrc, lastDst, 'all links restored.');
    });
    requestAnimationFrame(loop);
  }
  init();
})();
</script>

</body></html>
