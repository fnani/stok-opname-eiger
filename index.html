import React, { useState, useEffect, useMemo } from 'react';
import { 
  Plus, 
  Database, 
  TrendingUp, 
  RefreshCcw, 
  Sun, 
  Moon,
  ChevronLeft,
  ChevronRight,
  Box,
  LayoutGrid
} from 'lucide-react';

const API_URL = "https://script.google.com/macros/s/AKfycbxebGLNlw0UWezfr5FwJu4ZHv8wcCg_fWj3ZrdMe0VF1W1WsU05bXsoZ_QkjQ3jPWUU/exec";

const App = () => {
  const [view, setView] = useState('input');
  const [loading, setLoading] = useState(false);
  const [data, setData] = useState([]);
  const [currentTime, setCurrentTime] = useState(new Date());
  const [rowLimit, setRowLimit] = useState(10);
  const [currentPage, setCurrentPage] = useState(0);

  const [form, setForm] = useState({
    session: 'PAGI',
    a1989: '',
    mountaineering: '',
    kanan: '',
    tengah: '',
    kiri: '',
    womenJunior: '',
    riding: ''
  });

  const areas = [
    { id: 'a1989', label: '1989', color: 'bg-orange-500' },
    { id: 'mountaineering', label: 'MOUNTAINEERING', color: 'bg-emerald-500' },
    { id: 'kanan', label: 'AREA KANAN', color: 'bg-blue-500' },
    { id: 'tengah', label: 'AREA TENGAH', color: 'bg-purple-500' },
    { id: 'kiri', label: 'AREA KIRI', color: 'bg-pink-500' },
    { id: 'womenJunior', label: 'WOMEN & JUNIOR', color: 'bg-rose-500' },
    { id: 'riding', label: 'RIDING', color: 'bg-cyan-500' }
  ];

  useEffect(() => {
    const timer = setInterval(() => setCurrentTime(new Date()), 1000);
    fetchData();
    return () => clearInterval(timer);
  }, []);

  const fetchData = async () => {
    setLoading(true);
    try {
      const response = await fetch(API_URL);
      const result = await response.json();
      setData(result);
    } catch (e) { console.error(e); }
    finally { setLoading(false); }
  };

  const parseSheetDate = (dateStr) => {
    if (!dateStr) return { date: '-', time: '-', rawDate: new Date() };
    try {
      const parts = dateStr.split(' ');
      const dateParts = parts[0].split('/'); 
      const timeParts = parts[1] ? parts[1].split(':') : ['00', '00'];

      const year = parseInt(dateParts[2]) < 100 ? 2000 + parseInt(dateParts[2]) : parseInt(dateParts[2]);
      const month = parseInt(dateParts[1]) - 1; 
      const day = parseInt(dateParts[0]);
      
      const hours = parseInt(timeParts[0]);
      const mins = parseInt(timeParts[1]);

      const d = new Date(year, month, day, hours, mins);
      const monthsIndo = ['Jan', 'Feb', 'Mar', 'Apr', 'Mei', 'Jun', 'Jul', 'Agu', 'Sep', 'Okt', 'Nov', 'Des'];
      
      return {
        date: `${day.toString().padStart(2, '0')} ${monthsIndo[month]} ${year}`,
        time: `${hours.toString().padStart(2, '0')}.${mins.toString().padStart(2, '0')}`,
        day: day,
        rawDate: d
      };
    } catch (e) {
      const d = new Date(dateStr);
      return {
        date: d.toLocaleDateString('id-ID', { day: '2-digit', month: 'short', year: 'numeric' }),
        time: d.toLocaleTimeString('id-ID', { hour: '2-digit', minute: '2-digit' }).replace(':', '.'),
        day: d.getDate(),
        rawDate: d
      };
    }
  };

  const handleSubmit = async () => {
    setLoading(true);
    const total = areas.reduce((acc, curr) => acc + (parseInt(form[curr.id]) || 0), 0);
    const payload = { ...form, total, timestamp_str: new Date().toLocaleString('id-ID') };

    try {
      await fetch(API_URL, { method: 'POST', body: JSON.stringify(payload) });
      setForm({ session: 'PAGI', a1989: '', mountaineering: '', kanan: '', tengah: '', kiri: '', womenJunior: '', riding: '' });
      await fetchData();
      setView('history');
    } catch (e) { console.error(e); }
    finally { setLoading(false); }
  };

  const paginatedData = useMemo(() => {
    const sorted = [...data].reverse();
    return sorted.slice(currentPage * rowLimit, (currentPage + 1) * rowLimit);
  }, [data, currentPage, rowLimit]);

  const dateStatus = useMemo(() => {
    const statusMap = {};
    data.forEach(item => {
      const info = parseSheetDate(item.timestamp_str);
      const day = info.day;
      if (!statusMap[day]) statusMap[day] = { pagi: false, malam: false, valPagi: 0, valMalam: 0, dateLabel: info.date };
      if (item.session?.toUpperCase() === 'PAGI') { statusMap[day].pagi = true; statusMap[day].valPagi = item.total; }
      if (item.session?.toUpperCase() === 'MALAM') { statusMap[day].malam = true; statusMap[day].valMalam = item.total; }
    });
    return statusMap;
  }, [data]);

  return (
    <div className="min-h-screen bg-slate-50 pb-36 font-sans text-slate-900 overflow-x-hidden">
      {/* Header */}
      <header className="bg-white/80 backdrop-blur-md px-6 py-4 flex justify-between items-center sticky top-0 z-50 border-b border-slate-100 shadow-sm">
        <div className="flex items-center gap-3">
          <div className="bg-black p-2 rounded-xl text-white">
            <LayoutGrid size={18}/>
          </div>
          <div>
            <h1 className="font-black text-sm tracking-widest uppercase leading-none">EIGER PRO</h1>
            <p className="text-[9px] font-bold text-slate-400 uppercase tracking-tighter mt-1">Stok Opname System</p>
          </div>
        </div>
        <button onClick={fetchData} className={`p-2.5 rounded-full bg-slate-50 text-slate-400 hover:text-black transition-all ${loading ? 'animate-spin' : ''}`}>
          <RefreshCcw size={18} />
        </button>
      </header>

      <main className="max-w-xl mx-auto p-5 space-y-6">
        {/* Time Display */}
        <div className="bg-[#0F172A] rounded-[2.5rem] p-8 text-white flex justify-between items-center shadow-2xl relative overflow-hidden">
          <div className="relative z-10">
            <div className="flex items-center gap-2 mb-1">
               <div className="w-1.5 h-1.5 rounded-full bg-orange-500 animate-pulse"></div>
               <p className="text-[10px] font-bold text-slate-400 uppercase tracking-[0.2em]">{currentTime.toLocaleDateString('id-ID', { weekday: 'long' }).toUpperCase()}</p>
            </div>
            <h2 className="text-3xl font-black tracking-tight">
              {currentTime.getDate()} {currentTime.toLocaleDateString('id-ID', { month: 'short' })} {currentTime.getFullYear()}
            </h2>
          </div>
          <div className="text-right relative z-10">
            <p className="text-[10px] font-bold text-slate-400 uppercase tracking-[0.2em] mb-1">Waktu Lokal</p>
            <h2 className="text-3xl font-black tabular-nums">
              {currentTime.getHours().toString().padStart(2, '0')}.{currentTime.getMinutes().toString().padStart(2, '0')}
              <span className="text-lg opacity-30 ml-1">{currentTime.getSeconds().toString().padStart(2, '0')}</span>
            </h2>
          </div>
        </div>

        {/* --- VIEW: INPUT --- */}
        {view === 'input' && (
          <div className="space-y-4 animate-in fade-in slide-in-from-bottom-4 duration-500">
            {/* Session Switcher - FIXED LOGIC & NO EMOTICONS */}
            <div className="bg-white p-1.5 rounded-[2rem] shadow-sm border border-slate-100 flex gap-1">
              <button 
                onClick={() => setForm({...form, session: 'PAGI'})}
                className={`flex-1 py-4 rounded-[1.5rem] font-black text-[11px] flex items-center justify-center gap-2 transition-all ${form.session === 'PAGI' ? 'bg-orange-500 text-white shadow-lg shadow-orange-500/30 scale-100' : 'text-slate-400 bg-transparent'}`}
              >
                <Sun size={14} fill={form.session === 'PAGI' ? "currentColor" : "none"}/> PAGI
              </button>
              <button 
                onClick={() => setForm({...form, session: 'MALAM'})}
                className={`flex-1 py-4 rounded-[1.5rem] font-black text-[11px] flex items-center justify-center gap-2 transition-all ${form.session === 'MALAM' ? 'bg-[#1E293B] text-white shadow-lg shadow-slate-900/30 scale-100' : 'text-slate-400 bg-transparent'}`}
              >
                <Moon size={14} fill={form.session === 'MALAM' ? "currentColor" : "none"}/> MALAM
              </button>
            </div>

            {/* Input Cards */}
            <div className="space-y-3">
              {areas.map((area) => (
                <div key={area.id} className="bg-white rounded-[1.5rem] p-6 flex items-center justify-between border border-slate-100 shadow-sm relative overflow-hidden transition-all focus-within:ring-2 focus-within:ring-slate-100">
                  <div className={`absolute left-0 top-0 bottom-0 w-1.5 ${area.color}`}></div>
                  
                  <div className="pl-3 flex-1">
                    <span className="font-black text-[10px] text-slate-400 uppercase tracking-widest block mb-1">{area.label}</span>
                    <input 
                      type="number"
                      inputMode="numeric"
                      placeholder="0"
                      className="bg-transparent font-black text-2xl w-full focus:outline-none placeholder:text-slate-200"
                      value={form[area.id]}
                      onChange={(e) => setForm({...form, [area.id]: e.target.value})}
                    />
                  </div>
                  
                  <div className="text-slate-50">
                    <Box size={32} strokeWidth={1.5} />
                  </div>
                </div>
              ))}
            </div>

            <button 
              onClick={handleSubmit}
              disabled={loading}
              className="w-full bg-[#0F172A] text-white py-6 rounded-[2.5rem] font-black tracking-[0.2em] shadow-2xl flex items-center justify-center gap-3 active:scale-95 transition-all disabled:opacity-50"
            >
              {loading ? <RefreshCcw className="animate-spin" /> : <Plus size={20} strokeWidth={3} />}
              INPUT DATA
            </button>
          </div>
        )}

        {/* --- VIEW: HISTORY --- */}
        {view === 'history' && (
          <div className="space-y-4 animate-in fade-in duration-500">
            <div className="flex justify-between items-center px-2">
               <h3 className="font-black text-[10px] text-slate-300 uppercase tracking-[0.2em]">DATA HISTORY</h3>
               <div className="bg-white px-4 py-1.5 rounded-full border border-slate-100 shadow-sm">
                  <span className="text-[10px] font-black text-slate-800">Limit {rowLimit}</span>
               </div>
            </div>

            <div className="space-y-3">
              {paginatedData.map((item, i) => {
                const info = parseSheetDate(item.timestamp_str);
                const isPagi = item.session?.toUpperCase() === 'PAGI';
                return (
                  <div key={i} className="bg-white rounded-[2rem] p-5 flex items-center justify-between shadow-sm border border-slate-100">
                    <div className="flex items-center gap-4">
                      <div className={`w-12 h-12 rounded-2xl flex items-center justify-center ${isPagi ? 'bg-orange-50 text-orange-500' : 'bg-slate-100 text-slate-800'}`}>
                        {isPagi ? <Sun size={20}/> : <Moon size={20}/>}
                      </div>
                      <div>
                        <div className="flex items-center gap-2">
                           <p className="text-sm font-black text-slate-900">{info.date}</p>
                           <span className="text-slate-200 text-xs">|</span>
                           <p className="text-xs font-bold text-slate-400">{info.time}</p>
                        </div>
                        <p className="text-[9px] font-black text-slate-300 uppercase tracking-widest mt-0.5">{item.session}</p>
                      </div>
                    </div>
                    <div className="text-right">
                      <p className="text-xl font-black text-slate-900 leading-none">{item.total}</p>
                      <p className="text-[9px] font-bold text-slate-400 uppercase mt-1">Total Pcs</p>
                    </div>
                  </div>
                );
              })}
            </div>

            <div className="flex justify-center items-center gap-8 py-4">
               <button onClick={() => setCurrentPage(p => Math.max(0, p-1))} className="text-slate-300 hover:text-black transition-colors"><ChevronLeft size={24}/></button>
               <span className="text-xs font-black text-slate-400 uppercase tracking-widest">Page {currentPage + 1}</span>
               <button onClick={() => setCurrentPage(p => p+1)} className="text-slate-300 hover:text-black transition-colors"><ChevronRight size={24}/></button>
            </div>
          </div>
        )}

        {/* --- VIEW: SUMMARY --- */}
        {view === 'report' && (
          <div className="space-y-6 animate-in fade-in duration-500">
            <div className="bg-white p-8 rounded-[3rem] shadow-sm border border-slate-100">
              <h3 className="text-center font-black text-[10px] text-slate-300 tracking-[0.3em] mb-6 uppercase">FEBRUARI 2026</h3>
              <div className="grid grid-cols-7 gap-y-4">
                {['M', 'S', 'S', 'R', 'K', 'J', 'S'].map(d => <div key={d} className="text-center text-[10px] font-black text-slate-200">{d}</div>)}
                {Array.from({length: 28}, (_, i) => i + 1).map(day => {
                  const status = dateStatus[day];
                  const isToday = day === currentTime.getDate();
                  return (
                    <div key={day} className="flex flex-col items-center gap-1">
                      <div className={`w-9 h-9 flex items-center justify-center rounded-xl text-xs font-black transition-all ${isToday ? 'bg-orange-500 text-white shadow-lg shadow-orange-500/40' : 'text-slate-600'}`}>
                        {day}
                      </div>
                      <div className="flex gap-0.5">
                        {status?.pagi && <div className="w-1 h-1 rounded-full bg-orange-400"></div>}
                        {status?.malam && <div className="w-1 h-1 rounded-full bg-slate-400"></div>}
                      </div>
                    </div>
                  );
                })}
              </div>
            </div>

            <div className="space-y-3 px-2 pb-10">
              <h4 className="text-[10px] font-black text-slate-300 uppercase tracking-widest mb-4">LAPORAN BULAN INI</h4>
              {Object.keys(dateStatus).sort((a,b) => b-a).map(day => {
                const s = dateStatus[day];
                const diff = s.valPagi - s.valMalam;
                const isFull = s.pagi && s.malam;
                return (
                  <div key={day} className="bg-white p-6 rounded-[2rem] border border-slate-100 shadow-sm relative overflow-hidden">
                    <div className="flex justify-between items-center mb-6">
                      <div className="flex items-center gap-2">
                        <div className="w-2 h-2 rounded-full bg-slate-200"></div>
                        <span className="font-black text-xs uppercase tracking-tight text-slate-800">{s.dateLabel}</span>
                      </div>
                      <span className={`text-[9px] font-black px-3 py-1 rounded-full ${isFull ? 'bg-emerald-50 text-emerald-600' : 'bg-amber-50 text-amber-600'}`}>
                        {isFull ? 'COMPLETED' : 'INCOMPLETE'}
                      </span>
                    </div>
                    
                    <div className="flex justify-between items-center px-4">
                       <div className="text-center">
                         <p className="text-[9px] font-bold text-slate-300 uppercase mb-1 tracking-tighter">Pagi</p>
                         <p className="font-black text-lg">{s.valPagi || '-'}</p>
                       </div>
                       <div className="text-slate-100"><Box size={24} strokeWidth={1}/></div>
                       <div className="text-center">
                         <p className="text-[9px] font-bold text-slate-300 uppercase mb-1 tracking-tighter">Malam</p>
                         <p className="font-black text-lg">{s.valMalam || '-'}</p>
                       </div>
                    </div>

                    {isFull && (
                      <div className="mt-6 pt-4 border-t border-slate-50 flex justify-between items-center">
                        <span className="text-[10px] font-bold text-slate-300 uppercase">Selisih Mapping</span>
                        <span className={`font-black text-sm ${diff === 0 ? 'text-emerald-500' : 'text-rose-500'}`}>
                          {diff === 0 ? 'Balance' : (diff > 0 ? `+${diff}` : diff)} Pcs
                        </span>
                      </div>
                    )}
                  </div>
                );
              })}
            </div>
          </div>
        )}
      </main>

      {/* Navigation */}
      <div className="fixed bottom-8 left-1/2 -translate-x-1/2 w-[90%] max-w-sm z-50">
        <div className="bg-[#0F172A] p-2 rounded-[2.5rem] flex items-center justify-between shadow-2xl ring-1 ring-white/10">
          <button 
            onClick={() => setView('input')} 
            className={`flex-1 flex items-center justify-center gap-2 py-4 rounded-full transition-all ${view === 'input' ? 'bg-white text-black shadow-lg scale-105' : 'text-slate-500 hover:text-slate-300'}`}
          >
            <Plus size={20} />
            {view === 'input' && <span className="text-[11px] font-black tracking-tight">INPUT</span>}
          </button>
          
          <button 
            onClick={() => setView('history')} 
            className={`flex-1 flex items-center justify-center gap-2 py-4 rounded-full transition-all ${view === 'history' ? 'bg-white text-black shadow-lg scale-105' : 'text-slate-500 hover:text-slate-300'}`}
          >
            <Database size={20} />
            {view === 'history' && <span className="text-[11px] font-black tracking-tight uppercase">Data</span>}
          </button>
          
          <button 
            onClick={() => setView('report')} 
            className={`flex-1 flex items-center justify-center gap-2 py-4 rounded-full transition-all ${view === 'report' ? 'bg-white text-black shadow-lg scale-105' : 'text-slate-500 hover:text-slate-300'}`}
          >
            <TrendingUp size={20} />
            {view === 'report' && <span className="text-[11px] font-black tracking-tight uppercase">Summary</span>}
          </button>
        </div>
      </div>
    </div>
  );
};

export default App;
