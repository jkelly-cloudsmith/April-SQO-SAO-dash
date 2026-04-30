<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>SDR Pipeline Dashboard — Cloudsmith</title>
<script src="https://cdnjs.cloudflare.com/ajax/libs/Chart.js/4.4.1/chart.umd.js"></script>
<style>
  *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }
  body { font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', sans-serif; background: #f4f3ef; color: #1a1a18; padding: 2rem; }
  h1 { font-size: 17px; font-weight: 500; color: #1a1a18; }
  .page-header { display: flex; align-items: center; justify-content: space-between; margin-bottom: 1.5rem; flex-wrap: wrap; gap: 8px; }
  .subtitle { font-size: 12px; color: #888780; margin-top: 2px; }

  .stats { display: flex; gap: 12px; flex-wrap: wrap; margin-bottom: 1.5rem; }
  .stat-card { background: #fff; border: 0.5px solid #d3d1c7; border-radius: 10px; padding: 12px 18px; flex: 1; min-width: 110px; }
  .stat-label { font-size: 11px; color: #888780; margin-bottom: 4px; text-transform: uppercase; letter-spacing: 0.04em; }
  .stat-val { font-size: 26px; font-weight: 500; color: #1a1a18; line-height: 1; }
  .stat-val.green { color: #0f6e56; }
  .stat-delta { font-size: 12px; color: #888780; margin-top: 4px; }

  .charts-row { display: grid; grid-template-columns: 1fr 1fr; gap: 16px; margin-bottom: 1.5rem; }
  .chart-card { background: #fff; border: 0.5px solid #d3d1c7; border-radius: 10px; padding: 1.25rem; }
  .chart-title { font-size: 13px; font-weight: 500; color: #1a1a18; margin-bottom: 1rem; }
  .chart-wrap { position: relative; }

  .legend { display: flex; gap: 16px; font-size: 11px; color: #888780; margin-top: 12px; }
  .legend-item { display: flex; align-items: center; gap: 5px; }
  .legend-swatch { width: 10px; height: 10px; border-radius: 2px; }

  .list-card { background: #fff; border: 0.5px solid #d3d1c7; border-radius: 10px; padding: 1.25rem; }
  .list-header { display: flex; align-items: center; justify-content: space-between; margin-bottom: 1rem; flex-wrap: wrap; gap: 10px; }
  .list-title { font-size: 13px; font-weight: 500; color: #1a1a18; }

  .toggle-wrap { display: flex; align-items: center; gap: 8px; font-size: 12px; color: #888780; }
  .toggle { position: relative; width: 36px; height: 20px; cursor: pointer; }
  .toggle input { opacity: 0; width: 0; height: 0; }
  .slider { position: absolute; inset: 0; background: #b4b2a9; border-radius: 20px; transition: background 0.2s; }
  .slider:before { content: ''; position: absolute; height: 14px; width: 14px; left: 3px; top: 3px; background: #fff; border-radius: 50%; transition: transform 0.2s; }
  input:checked + .slider { background: #1d9e75; }
  input:checked + .slider:before { transform: translateX(16px); }

  .source-section { margin-bottom: 1rem; }
  .source-header { display: flex; align-items: center; justify-content: space-between; padding: 5px 10px; border-radius: 7px; margin-bottom: 5px; background: #f4f3ef; }
  .source-header.other { border: 1px dashed #c8c6bc; background: transparent; }
  .source-name { font-size: 12px; font-weight: 500; color: #1a1a18; }
  .source-right { display: flex; align-items: center; gap: 8px; }
  .sao-badge { font-size: 11px; color: #1d9e75; }
  .other-label { font-size: 11px; color: #888780; }
  .source-count { font-size: 11px; color: #888780; background: #fff; border: 0.5px solid #d3d1c7; border-radius: 20px; padding: 1px 7px; }
  .company-grid { display: flex; flex-wrap: wrap; gap: 5px; padding: 0 2px; }
  .company-pill { font-size: 11px; padding: 3px 9px; border-radius: 20px; border: 0.5px solid #d3d1c7; background: #fff; color: #1a1a18; }
  .company-pill.sao { background: #e1f5ee; border-color: #5dcaa5; color: #085041; }

  @media (max-width: 600px) { .charts-row { grid-template-columns: 1fr; } }
</style>
</head>
<body>

<div class="page-header">
  <div>
    <h1>SDR Pipeline Dashboard</h1>
    <div class="subtitle">Cloudsmith · Meetings booked from #team-sdr · 2026</div>
  </div>
</div>

<div class="stats">
  <div class="stat-card">
    <div class="stat-label">Meetings booked</div>
    <div class="stat-val" id="stat-meetings">56</div>
    <div class="stat-delta">across 6 sources</div>
  </div>
  <div class="stat-card">
    <div class="stat-label">Became SAOs</div>
    <div class="stat-val green" id="stat-saos">28</div>
    <div class="stat-delta">from #team-sdr meetings</div>
  </div>
  <div class="stat-card">
    <div class="stat-label">SAO rate</div>
    <div class="stat-val green" id="stat-rate">50%</div>
    <div class="stat-delta">meetings → SAO</div>
  </div>
  <div class="stat-card">
    <div class="stat-label">Total SAOs</div>
    <div class="stat-val green">44</div>
    <div class="stat-delta">incl. 15 not in channel</div>
  </div>
  <div class="stat-card">
    <div class="stat-label">Top source</div>
    <div class="stat-val" style="font-size:20px;">Referral</div>
    <div class="stat-delta">100% conversion</div>
  </div>
</div>

<div class="charts-row">
  <div class="chart-card">
    <div class="chart-title">Meetings booked by source</div>
    <div class="chart-wrap" style="height: 240px;">
      <canvas id="chart-volume" role="img" aria-label="Stacked bar chart of meetings booked per source, split by SAO and non-SAO">R4D: 22 meetings (13 SAO). Outbound: 13 (4 SAO). Qualified: 11 (5 SAO). Events: 6 (4 SAO). Referral: 2 (2 SAO). Midbound: 2 (0 SAO).</canvas>
    </div>
    <div class="legend">
      <div class="legend-item"><div class="legend-swatch" style="background:#1d9e75;"></div> Became SAO</div>
      <div class="legend-item"><div class="legend-swatch" style="background:#d3d1c7;"></div> Meeting only</div>
    </div>
  </div>

  <div class="chart-card">
    <div class="chart-title">SAO conversion rate by source</div>
    <div class="chart-wrap" style="height: 240px;">
      <canvas id="chart-rate" role="img" aria-label="Horizontal bar chart of SAO conversion rate per source">Referral: 100%. Events: 67%. R4D: 59%. Qualified: 45%. Outbound: 31%. Midbound: 0%.</canvas>
    </div>
  </div>
</div>

<div class="list-card">
  <div class="list-header">
    <div class="list-title">All companies</div>
    <div class="toggle-wrap">
      <span>SAOs only</span>
      <label class="toggle">
        <input type="checkbox" id="sao-toggle">
        <span class="slider"></span>
      </label>
    </div>
  </div>
  <div id="source-list"></div>
</div>

<script>
const saoSet = new Set([
  '1Password','9fin','AJ Bell','AlphaSense','Aurizon','Avinode','Bastion','Bawag Group',
  'BlueVoyant','Brivo','Cloud Software Group','CoinsPaid','Ctrl Alt','Dohop','EGYM',
  'Firefly Capital','Freeport-McMoRan','Funnel','Hennes & Mauritz','HDI Versicherung',
  'INFORM Software','Insight Partners','ManyPets Insurance','Migros-Genossenschafts-Bund',
  'NX1','Orrick','Panasonic Avionics','Policy Expert','ProDeal','Quantifi','Resonate',
  'Savvas','Schwarz Digits','Sigma Computing','Synthesia','Tenstreet','Trexity',
  'TWG Global','Wayflyer','Wealth.com','WellSky','Whitespace Solutions','Wolters Kluwer'
]);

const sources = [
  { name: 'R4D', companies: ['Avinode','Brivo','Hennes & Mauritz','Insight Partners','Las Vegas Sands','NX1','OpenMind Networks','Orrick','ProDeal','Sonar','Webpros','WellSky','WorkOS','Firefly Capital','ManyPets Insurance','Prior IT Services','Savvas','Liminal','NielsenIQ','onXmaps','CoinsPaid','Panasonic Avionics'] },
  { name: 'Outbound', companies: ['Bastion','Dohop','EGYM','Fenergo','Idox plc','iManage','Kongsberg Maritime','Nykredit','Smarsh','Takeda Pharmaceutical','Yahoo','Built','Funnel'] },
  { name: 'Qualified', companies: ['Databricks','Fordefi','Kraken','Policy Expert','Profusion','SlingShot EDU','TruStone Financial Credit Union','Wayflyer','Tenstreet','Trexity','Resonate'] },
  { name: 'Events', companies: ['DSV','HDI Versicherung','Nomadic Labs','Schwarz Digits','INFORM Software','Synthesia'] },
  { name: 'Referral', companies: ['1Password','Wealth.com'] },
  { name: 'Midbound', companies: ['Toyota Racing Development','Impel AI'] },
  { name: 'Other', isOther: true, companies: ['9fin','AJ Bell','AlphaSense','Aurizon','Bawag Group','BlueVoyant','Cloud Software Group','Ctrl Alt','Freeport-McMoRan','Migros-Genossenschafts-Bund','Quantifi','Sigma Computing','TWG Global','Whitespace Solutions','Wolters Kluwer'] }
];

const channelSources = sources.filter(s => !s.isOther);
const channelTotal = channelSources.reduce((a, s) => a + s.companies.length, 0);
const channelSAOs = channelSources.reduce((a, s) => a + s.companies.filter(c => saoSet.has(c)).length, 0);

document.getElementById('stat-meetings').textContent = channelTotal;
document.getElementById('stat-saos').textContent = channelSAOs;
document.getElementById('stat-rate').textContent = Math.round(channelSAOs / channelTotal * 100) + '%';

const volumeData = channelSources.map(s => ({
  name: s.name,
  sao: s.companies.filter(c => saoSet.has(c)).length,
  nonSao: s.companies.filter(c => !saoSet.has(c)).length,
  total: s.companies.length
})).sort((a, b) => b.total - a.total);

const rateData = channelSources.map(s => ({
  name: s.name,
  rate: Math.round(s.companies.filter(c => saoSet.has(c)).length / s.companies.length * 100)
})).sort((a, b) => b.rate - a.rate);

new Chart(document.getElementById('chart-volume'), {
  type: 'bar',
  data: {
    labels: volumeData.map(d => d.name),
    datasets: [
      {
        label: 'Became SAO',
        data: volumeData.map(d => d.sao),
        backgroundColor: '#1d9e75',
        borderRadius: 0
      },
      {
        label: 'Meeting only',
        data: volumeData.map(d => d.nonSao),
        backgroundColor: '#d3d1c7',
        borderRadius: 3
      }
    ]
  },
  options: {
    responsive: true,
    maintainAspectRatio: false,
    plugins: { legend: { display: false } },
    scales: {
      x: {
        stacked: true,
        grid: { display: false },
        ticks: { font: { size: 11 }, color: '#888780' },
        border: { display: false }
      },
      y: {
        stacked: true,
        grid: { color: '#f0efe8' },
        ticks: { font: { size: 11 }, color: '#888780', stepSize: 5 },
        border: { display: false }
      }
    }
  }
});

new Chart(document.getElementById('chart-rate'), {
  type: 'bar',
  data: {
    labels: rateData.map(d => d.name),
    datasets: [{
      label: 'SAO conversion rate',
      data: rateData.map(d => d.rate),
      backgroundColor: rateData.map(d => d.rate >= 60 ? '#1d9e75' : d.rate >= 40 ? '#5dcaa5' : '#9fe1cb'),
      borderRadius: 3
    }]
  },
  options: {
    indexAxis: 'y',
    responsive: true,
    maintainAspectRatio: false,
    plugins: {
      legend: { display: false },
      tooltip: {
        callbacks: { label: ctx => ' ' + ctx.raw + '%' }
      }
    },
    scales: {
      x: {
        grid: { color: '#f0efe8' },
        ticks: { font: { size: 11 }, color: '#888780', callback: v => v + '%' },
        border: { display: false },
        max: 100
      },
      y: {
        grid: { display: false },
        ticks: { font: { size: 11 }, color: '#888780' },
        border: { display: false }
      }
    }
  }
});

const container = document.getElementById('source-list');
const toggle = document.getElementById('sao-toggle');

function render(saoOnly) {
  container.innerHTML = '';
  sources.forEach(src => {
    const filtered = saoOnly
      ? (src.isOther ? src.companies : src.companies.filter(c => saoSet.has(c)))
      : src.companies;
    if (filtered.length === 0) return;

    const section = document.createElement('div');
    section.className = 'source-section';

    const header = document.createElement('div');
    header.className = 'source-header' + (src.isOther ? ' other' : '');

    const saoInGroup = filtered.filter(c => saoSet.has(c)).length;
    let badge = '';
    if (!saoOnly && !src.isOther) {
      badge = '<span class="sao-badge">' + saoInGroup + ' SAO' + (saoInGroup !== 1 ? 's' : '') + '</span>';
    }
    const otherLabel = src.isOther ? '<span class="other-label">not in #team-sdr</span>' : '';
    header.innerHTML = '<span class="source-name">' + src.name + '</span><div class="source-right">' + badge + otherLabel + '<span class="source-count">' + filtered.length + '</span></div>';
    section.appendChild(header);

    const grid = document.createElement('div');
    grid.className = 'company-grid';
    filtered.forEach(c => {
      const pill = document.createElement('span');
      pill.className = 'company-pill' + (saoSet.has(c) ? ' sao' : '');
      pill.textContent = c;
      grid.appendChild(pill);
    });
    section.appendChild(grid);
    container.appendChild(section);
  });
}

render(false);
toggle.addEventListener('change', () => render(toggle.checked));
</script>
</body>
</html>
