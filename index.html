import React, { useState, useEffect } from 'react';
import { 
  CheckCircle2, Circle, Activity, FileText, Calendar, Info, 
  AlertCircle, HelpCircle, X, ArrowRight, Footprints, Flame, 
  Timer, Pill, Stethoscope, ChevronRight, ChevronDown, 
  TrendingUp, Thermometer, Moon, RotateCcw
} from 'lucide-react';

// Genera le attività in base alla settimana di terapia (con sessioni e dettagli)
const getTasksForWeek = (week) => {
  if (week <= 2) {
    return [
      { id: 1, text: 'Crioterapia (15 min)', icon: Thermometer, detail: "Borsa del ghiaccio avvolta in un panno, mai a contatto diretto.", sessions: 3, doneCount: 0 },
      { id: 2, text: 'Massaggio con Arnica 90%', icon: Moon, detail: "Applicare la notte sul tallone con movimenti circolari profondi per 3-5 min.", sessions: 1, doneCount: 0 },
      { id: 3, text: 'Boswellia / Curcumina', icon: Pill, detail: "Antinfiammatorio naturale. Assumere con un pasto.", sessions: 1, doneCount: 0 },
      { id: 4, text: 'Uso rigoroso tallonette', icon: Footprints, detail: "Mantieni le tallonette in ENTRAMBE le scarpe tutto il giorno.", sessions: 1, doneCount: 0 }
    ];
  } else {
    // Dalla settimana 3 in poi, fase riabilitativa
    return [
      { id: 1, text: 'Stretching Fascia Plantare', icon: Activity, detail: "Siediti, incrocia il piede sul ginocchio opposto e tira le dita verso di te. 3 serie da 30s.", sessions: 3, doneCount: 0 },
      { id: 2, text: "Stretching Tendine d'Achille", icon: Activity, detail: "In piedi verso un muro, tallone a terra, inclina il corpo in avanti. 3 serie da 30s.", sessions: 3, doneCount: 0 },
      { id: 3, text: 'Eccentrici polpaccio (3x15)', icon: Footprints, detail: "Su un gradino, sali su entrambi i piedi, scendi lentamente solo sul piede infortunato.", sessions: 1, doneCount: 0 },
      { id: 4, text: 'Massaggio scarico serale', icon: Moon, detail: "Massaggia la fascia plantare con una pallina da tennis o le mani prima di dormire.", sessions: 1, doneCount: 0 }
    ];
  }
};

export default function App() {
  const [activeTab, setActiveTab] = useState('oggi');
  const [showTutorial, setShowTutorial] = useState(false);
  const [expandedTask, setExpandedTask] = useState(null);
  
  // Stato principale dell'app
  const [appState, setAppState] = useState(() => {
    const saved = localStorage.getItem('podoRehabState');
    const today = new Date().toDateString();
    
    if (saved) {
      const parsed = JSON.parse(saved);
      
      // Controllo nuovo giorno: archivia ieri e resetta spunte
      if (parsed.lastDate !== today) {
        const start = new Date(parsed.startDate);
        const debugDays = parsed.debugDayOffset || 0;
        
        const now = new Date();
        now.setDate(now.getDate() + debugDays); 
        
        const diffTime = Math.abs(now - start);
        const diffDays = Math.ceil(diffTime / (1000 * 60 * 60 * 24));
        const currentWeek = Math.floor(diffDays / 7) + 1;

        // Archiviazione giorno precedente
        const archivedDay = {
          date: parsed.lastDate,
          tasks: parsed.tasks,
          pain: parsed.painValue || 5
        };

        const newTasks = getTasksForWeek(currentWeek);
        return { 
          ...parsed, 
          history: [...(parsed.history || []), archivedDay],
          lastDate: today, 
          currentWeek, 
          tasks: newTasks,
          painValue: parsed.painValue || 5 // Mantieni l'ultimo dolore come base
        };
      }
      return parsed;
    }
    
    // Primissimo avvio
    return {
      startDate: new Date().toISOString(),
      lastDate: today,
      currentWeek: 1,
      debugDayOffset: 0,
      tasks: getTasksForWeek(1),
      painValue: 5,
      history: [],
      isFirstVisit: true
    };
  });

  useEffect(() => {
    if (appState.isFirstVisit) {
      setShowTutorial(true);
      setAppState(prev => ({ ...prev, isFirstVisit: false }));
    }
    localStorage.setItem('podoRehabState', JSON.stringify(appState));
  }, [appState]);

  const incrementTask = (id, e) => {
    e.stopPropagation();
    setAppState(prev => ({
      ...prev,
      tasks: prev.tasks.map(t => t.id === id && t.doneCount < t.sessions ? { ...t, doneCount: t.doneCount + 1 } : t)
    }));
  };

  const resetTask = (id, e) => {
    e.stopPropagation();
    setAppState(prev => ({
      ...prev,
      tasks: prev.tasks.map(t => t.id === id ? { ...t, doneCount: 0 } : t)
    }));
  };

  const setPainValue = (val) => {
    setAppState(prev => ({ ...prev, painValue: val }));
  };

  const toggleTaskExpansion = (id) => {
    setExpandedTask(expandedTask === id ? null : id);
  };

  const simulateNextWeek = () => {
    const today = new Date().toDateString();
    setAppState(prev => {
      const newOffset = (prev.debugDayOffset || 0) + 7;
      const start = new Date(prev.startDate);
      const fakeNow = new Date();
      fakeNow.setDate(fakeNow.getDate() + newOffset);
      
      const diffTime = Math.abs(fakeNow - start);
      const diffDays = Math.ceil(diffTime / (1000 * 60 * 60 * 24));
      const currentWeek = Math.floor(diffDays / 7) + 1;
      
      // Archivia fittiziamente per mostrare il grafico
      const archivedDay = { date: `Giorno ${(prev.debugDayOffset || 0) + 7}`, tasks: prev.tasks, pain: prev.painValue || 5 };

      return {
        ...prev,
        history: [...(prev.history || []), archivedDay],
        debugDayOffset: newOffset,
        currentWeek: currentWeek,
        tasks: getTasksForWeek(currentWeek),
        lastDate: today 
      };
    });
    alert('Hai viaggiato nel tempo di 1 settimana! Controlla i tuoi task di "Oggi".');
  };

  const resetTime = () => {
    const today = new Date().toDateString();
    setAppState({
      startDate: new Date().toISOString(),
      lastDate: today,
      currentWeek: 1,
      debugDayOffset: 0,
      tasks: getTasksForWeek(1),
      painValue: 5,
      history: [],
      isFirstVisit: false
    });
    alert('Tempo resettato alla Settimana 1.');
  };

  // Calcoli progresso
  const totalSessions = appState.tasks.reduce((acc, t) => acc + t.sessions, 0);
  const completedSessions = appState.tasks.reduce((acc, t) => acc + t.doneCount, 0);
  const progress = totalSessions > 0 ? Math.round((completedSessions / totalSessions) * 100) : 0;
  
  // Colore del dolore
  const painColor = appState.painValue <= 3 ? 'text-green-500' : appState.painValue <= 6 ? 'text-amber-500' : 'text-red-500';
  const painBg = appState.painValue <= 3 ? 'bg-green-500' : appState.painValue <= 6 ? 'bg-amber-500' : 'bg-red-500';

  const renderOggi = () => (
    <div className="space-y-6 animate-in fade-in duration-500 slide-in-from-bottom-4 pb-4">
      {/* Scheda Riepilogo */}
      <div className="bg-gradient-to-br from-blue-600 to-indigo-700 p-6 rounded-3xl shadow-lg text-white transform transition-all hover:scale-[1.02]">
        <h2 className="text-xl font-bold mb-1 opacity-90">Programma Giornaliero</h2>
        <div className="flex items-center space-x-2 text-blue-100 mb-4">
          <Calendar className="w-4 h-4" />
          <span className="text-sm font-medium">Settimana {appState.currentWeek} di Terapia</span>
        </div>
        
        <div className="mt-4 flex items-center justify-between">
          <div className="text-sm font-medium text-blue-50">Completamento</div>
          <div className="text-lg font-bold">{progress}%</div>
        </div>
        <div className="w-full bg-blue-900/40 rounded-full h-3 mt-2 overflow-hidden shadow-inner">
          <div 
            className="bg-white h-3 rounded-full transition-all duration-1000 ease-out relative" 
            style={{ width: `${progress}%` }}
          >
            <div className="absolute inset-0 bg-white/30 animate-pulse"></div>
          </div>
        </div>
      </div>

      {/* Pain Slider */}
      <div className="bg-white p-5 rounded-2xl border border-slate-100 shadow-sm">
        <div className="flex justify-between items-end mb-2">
          <span className="text-sm font-bold text-slate-700 flex items-center">
            <Activity className="w-4 h-4 mr-1.5 text-slate-400" /> Dolore Oggi
          </span>
          <span className={`text-2xl font-black ${painColor}`}>{appState.painValue}/10</span>
        </div>
        <div className="relative h-3 bg-gradient-to-r from-green-400 via-amber-400 to-red-500 rounded-full mt-4">
          <input 
            type="range" min="1" max="10" 
            value={appState.painValue} 
            onChange={(e) => setPainValue(Number(e.target.value))}
            className="absolute inset-0 w-full opacity-0 cursor-pointer"
          />
          <div 
            className="absolute top-1/2 -translate-y-1/2 w-5 h-5 bg-white rounded-full border-2 shadow-md pointer-events-none transition-all duration-150"
            style={{ left: `calc(${(appState.painValue - 1) * 100 / 9}% - 10px)`, borderColor: appState.painValue <= 3 ? '#22c55e' : appState.painValue <= 6 ? '#f59e0b' : '#ef4444' }}
          ></div>
        </div>
        <div className="flex justify-between mt-2 text-[10px] uppercase font-bold text-slate-400">
          <span>Assente</span>
          <span>Severo</span>
        </div>
      </div>

      {/* Task List */}
      <div className="space-y-3">
        <h3 className="font-bold text-slate-800 px-2 flex items-center">
          <Activity className="w-5 h-5 mr-2 text-blue-600" />
          Da fare oggi
        </h3>
        
        <div className="grid gap-3">
          {appState.tasks.map(task => {
            const TaskIcon = task.icon || Circle;
            const isDone = task.doneCount >= task.sessions;
            const isExpanded = expandedTask === task.id;
            const taskProgress = (task.doneCount / task.sessions) * 100;

            return (
              <div 
                key={task.id} 
                className={`overflow-hidden rounded-2xl transition-all duration-300 ${
                  isDone ? 'bg-blue-50/50 border border-blue-100 shadow-sm' : 'bg-white border border-slate-100 shadow-md'
                }`}
              >
                <div 
                  onClick={() => toggleTaskExpansion(task.id)}
                  className="flex items-center p-4 cursor-pointer"
                >
                  <div className={`p-2.5 rounded-xl mr-3 transition-colors duration-300 ${isDone ? 'bg-blue-100 text-blue-600' : 'bg-slate-50 text-slate-400'}`}>
                    {isDone ? <CheckCircle2 className="w-6 h-6" /> : <TaskIcon className="w-6 h-6" />}
                  </div>
                  
                  <div className="flex-1 min-w-0">
                    <p className={`font-semibold truncate transition-colors ${isDone ? 'text-slate-500 line-through' : 'text-slate-800'}`}>
                      {task.text}
                    </p>
                    
                    {/* Barra progresso singola task (se > 1 sessione) */}
                    {task.sessions > 1 && (
                      <div className="flex items-center gap-2 mt-1.5">
                        <div className="flex-1 h-1.5 bg-slate-100 rounded-full overflow-hidden">
                          <div className={`h-full transition-all duration-500 ${isDone ? 'bg-blue-400' : 'bg-blue-600'}`} style={{ width: `${taskProgress}%` }}></div>
                        </div>
                        <span className="text-[10px] font-bold text-slate-400">{task.doneCount}/{task.sessions}</span>
                      </div>
                    )}
                  </div>

                  <div className="flex items-center gap-2 ml-2">
                    {task.doneCount > 0 && (
                      <button onClick={(e) => resetTask(task.id, e)} className="p-2 text-slate-300 hover:text-slate-500 transition-colors">
                        <RotateCcw className="w-4 h-4" />
                      </button>
                    )}
                    <button 
                      onClick={(e) => incrementTask(task.id, e)}
                      disabled={isDone}
                      className={`px-3 py-1.5 rounded-lg font-bold text-sm transition-colors ${
                        isDone ? 'bg-blue-100/50 text-blue-400 cursor-default' : 'bg-blue-600 text-white hover:bg-blue-700 active:scale-95 shadow-sm'
                      }`}
                    >
                      {isDone ? 'Fatto' : '+1'}
                    </button>
                  </div>
                </div>

                {/* Dettagli espansi */}
                {isExpanded && (
                  <div className="px-4 pb-4 pt-1 border-t border-slate-50 bg-slate-50/50">
                    <p className="text-sm text-slate-600 leading-relaxed mt-2">
                      <strong className="text-slate-800 font-semibold mr-1">Istruzioni:</strong> 
                      {task.detail}
                    </p>
                  </div>
                )}
              </div>
            );
          })}
        </div>
      </div>

      <div className="bg-gradient-to-r from-amber-50 to-orange-50 p-5 rounded-2xl border border-amber-100 flex items-start shadow-sm mt-6">
        <AlertCircle className="w-6 h-6 text-amber-500 mt-0.5 flex-shrink-0 animate-pulse" />
        <div className="ml-3">
          <h4 className="text-sm font-bold text-amber-800">Regola d'oro costante</h4>
          <p className="text-xs text-amber-700 mt-1 leading-relaxed">
            Non camminare mai scalzo! Usa sempre una ciabatta con tacco di 2-3 cm anche in casa per scaricare la spina calcaneare.
          </p>
        </div>
      </div>
    </div>
  );

  const renderProtocollo = () => (
    <div className="space-y-4 animate-in fade-in duration-500 slide-in-from-bottom-4">
      <h2 className="text-xl font-bold text-slate-800 mb-2 px-1 flex items-center">
        <Stethoscope className="w-6 h-6 mr-2 text-indigo-600" />
        Linee Guida Mediche
      </h2>
      <p className="text-sm text-slate-500 px-1 mb-4">Il tuo percorso terapeutico completo.</p>
      
      {[
        { title: "Diagnosi", icon: Activity, color: "text-orange-500", bg: "bg-orange-50", items: ["Fasciopatia plantare con spina calcaneare", "Tendinosi inserzionale d'Achille"] },
        { title: "Gestione Dolore", icon: Thermometer, color: "text-blue-500", bg: "bg-blue-50", items: ["Crioterapia 15 min (mai a contatto diretto)", "Massaggio serale Arnica 90%"] },
        { title: "Calzature e Ortesi", icon: Footprints, color: "text-indigo-500", bg: "bg-indigo-50", items: [<span>Usa tallonette in silicone in <strong className="mx-1">entrambe</strong> le scarpe.</span>, "Evita scarpe piatte (es. Converse)", "In casa sempre ciabatta con tacco 2-3cm"] },
        { title: "Integrazione", icon: Pill, color: "text-emerald-500", bg: "bg-emerald-50", items: ["Boswellia / Curcumina per 15-20gg", "Collagene Tipo I + Vit C (ciclo 2 mesi)"] },
        { title: "Stile di Vita", icon: Flame, color: "text-red-500", bg: "bg-red-50", items: ["Sospendere fumo (migliora microcircolo)", "Sport concessi: nuoto, bicicletta"] }
      ].map((section, idx) => {
        const Icon = section.icon;
        return (
          <div key={idx} className="bg-white p-5 rounded-2xl shadow-sm border border-slate-100 transition-transform hover:-translate-y-1 duration-300">
            <div className="flex items-center mb-3 pb-3 border-b border-slate-50">
              <div className={`${section.bg} p-2 rounded-xl`}>
                <Icon className={`w-5 h-5 ${section.color}`} />
              </div>
              <h3 className="font-bold text-slate-800 ml-3">{section.title}</h3>
            </div>
            <ul className="space-y-2.5 text-sm text-slate-600 ml-1">
              {section.items.map((item, i) => (
                <li key={i} className="flex items-start">
                  <ArrowRight className="w-4 h-4 mr-2 text-slate-300 mt-0.5 flex-shrink-0"/> 
                  <span className="leading-snug">{item}</span>
                </li>
              ))}
            </ul>
          </div>
        )
      })}
    </div>
  );

  const renderTimeline = () => (
    <div className="space-y-6 animate-in fade-in duration-500 slide-in-from-bottom-4">
      <h2 className="text-xl font-bold text-slate-800 mb-4 px-1 flex items-center">
        <Timer className="w-6 h-6 mr-2 text-blue-600" />
        Fasi di Recupero
      </h2>
      
      <div className="bg-white p-6 rounded-3xl shadow-md border border-slate-100">
        <div className="relative border-l-2 border-slate-100 ml-4 space-y-10 pb-4">
          
          {/* FASE 1 */}
          <div className="relative pl-8 transition-opacity duration-300">
            <div className={`absolute -left-[11px] top-0 w-5 h-5 rounded-full border-4 border-white shadow-sm ${appState.currentWeek <= 2 ? 'bg-blue-600 ring-4 ring-blue-100 animate-pulse' : 'bg-green-500'}`}></div>
            <h3 className={`font-bold ${appState.currentWeek <= 2 ? 'text-blue-600 text-lg' : 'text-slate-700'}`}>
              Settimana 1-2
              {appState.currentWeek > 2 && <span className="ml-2 text-xs bg-green-100 text-green-700 px-2 py-1 rounded-full">Completata</span>}
            </h3>
            <p className="text-sm text-slate-500 font-medium mb-2">Fase Acuta - Riduzione Infiammazione</p>
            <div className={`p-4 rounded-xl text-sm ${appState.currentWeek <= 2 ? 'bg-blue-50 text-blue-800 border border-blue-100' : 'bg-slate-50 text-slate-500'}`}>
              Ghiaccio, massaggi, tallonette in silicone. Riposo da sport di impatto. Ridurre il fumo.
            </div>
          </div>

          {/* FASE 2 */}
          <div className={`relative pl-8 transition-opacity duration-300 ${appState.currentWeek < 3 ? 'opacity-50' : ''}`}>
            <div className={`absolute -left-[11px] top-0 w-5 h-5 rounded-full border-4 border-white shadow-sm ${appState.currentWeek >= 3 ? 'bg-blue-600 ring-4 ring-blue-100 animate-pulse' : 'bg-slate-200'}`}></div>
            <h3 className={`font-bold ${appState.currentWeek >= 3 ? 'text-blue-600 text-lg' : 'text-slate-700'}`}>Settimana 3+</h3>
            <p className="text-sm text-slate-500 font-medium mb-2">Riabilitazione Attiva</p>
            <div className={`p-4 rounded-xl text-sm ${appState.currentWeek >= 3 ? 'bg-blue-50 text-blue-800 border border-blue-100' : 'bg-slate-50 text-slate-500'}`}>
              Esercizi di stretching per la fascia plantare, tendine d'Achille ed esercizi di rinforzo eccentrico.
            </div>
          </div>

          {/* FOLLOW UP */}
          <div className="relative pl-8 opacity-60">
            <div className="absolute -left-[11px] top-0 w-5 h-5 bg-slate-200 rounded-full border-4 border-white shadow-sm"></div>
            <h3 className="font-bold text-slate-700">Mese 2</h3>
            <p className="text-sm text-slate-500 font-medium mb-2">Follow-up Medico</p>
            <div className="bg-slate-50 p-4 rounded-xl text-sm text-slate-600 border border-slate-100">
              Valutazione dei progressi. Se il dolore persiste, verrà valutata la terapia con Onde d'Urto o infiltrazioni.
            </div>
          </div>

        </div>
      </div>

      {/* STRUMENTI DI DEBUG */}
      <div className="mt-8 p-4 bg-slate-800 rounded-2xl text-slate-300 text-xs">
        <p className="mb-2 uppercase font-bold tracking-wider flex items-center">
          <AlertCircle className="w-4 h-4 mr-1" /> 
          Avanti Veloce
        </p>
        <p className="mb-3">Simula il passare delle settimane per vedere come l'app si aggiorna e riempie il Trend.</p>
        <div className="flex space-x-2">
          <button onClick={simulateNextWeek} className="bg-slate-700 hover:bg-slate-600 px-3 py-2 rounded-lg text-white font-medium transition-colors">
            +1 Settimana
          </button>
          <button onClick={resetTime} className="bg-red-900/50 hover:bg-red-800/80 px-3 py-2 rounded-lg text-red-200 font-medium transition-colors">
            Reset App
          </button>
        </div>
      </div>
    </div>
  );

  const renderAndamento = () => {
    const history = appState.history || [];
    const recentHistory = history.slice(-7); // Mostra ultimi 7 giorni

    return (
      <div className="space-y-6 animate-in fade-in duration-500 slide-in-from-bottom-4">
        <h2 className="text-xl font-bold text-slate-800 mb-4 px-1 flex items-center">
          <TrendingUp className="w-6 h-6 mr-2 text-indigo-600" />
          Trend Dolore
        </h2>

        {history.length === 0 ? (
          <div className="bg-white p-8 rounded-3xl text-center border border-slate-100 shadow-sm">
            <TrendingUp className="w-12 h-12 text-slate-200 mx-auto mb-3" />
            <p className="text-slate-500 text-sm">Nessun dato archiviato.<br/>Il grafico si aggiornerà in automatico domani.</p>
          </div>
        ) : (
          <div className="bg-white p-5 rounded-3xl shadow-sm border border-slate-100">
            <p className="text-xs font-bold text-slate-400 uppercase tracking-wider mb-6 text-center">Ultimi giorni</p>
            
            <div className="flex items-end justify-around h-40 gap-2 mb-2">
              {recentHistory.map((day, i) => {
                const pain = day.pain || 5;
                const h = Math.max(10, (pain / 10) * 100); 
                const barColor = pain <= 3 ? 'bg-green-500' : pain <= 6 ? 'bg-amber-400' : 'bg-red-500';
                
                return (
                  <div key={i} className="flex flex-col items-center flex-1 group">
                    <span className="text-[10px] font-bold text-slate-600 mb-1 opacity-0 group-hover:opacity-100 transition-opacity">{pain}</span>
                    <div className="w-full relative bg-slate-50 rounded-t-lg h-full flex items-end overflow-hidden">
                      <div className={`w-full rounded-t-lg transition-all duration-700 ease-out ${barColor}`} style={{ height: `${h}%` }}></div>
                    </div>
                  </div>
                );
              })}
            </div>
            
            <div className="flex items-center justify-center gap-4 mt-6 pt-4 border-t border-slate-50">
              <div className="flex items-center gap-1.5"><div className="w-2.5 h-2.5 rounded-full bg-green-500"></div><span className="text-xs text-slate-500">Lieve</span></div>
              <div className="flex items-center gap-1.5"><div className="w-2.5 h-2.5 rounded-full bg-amber-400"></div><span className="text-xs text-slate-500">Moderato</span></div>
              <div className="flex items-center gap-1.5"><div className="w-2.5 h-2.5 rounded-full bg-red-500"></div><span className="text-xs text-slate-500">Severo</span></div>
            </div>
          </div>
        )}

        <div className="mt-8">
          <h3 className="font-bold text-slate-800 px-2 mb-3">Storico Attività</h3>
          <div className="space-y-3">
            {[...history].reverse().slice(0, 5).map((day, i) => {
              const total = day.tasks.reduce((a, t) => a + (t.sessions || 1), 0);
              const done = day.tasks.reduce((a, t) => a + (t.doneCount || (t.done ? 1 : 0)), 0);
              const pct = total > 0 ? Math.round((done / total) * 100) : 0;
              
              return (
                <div key={i} className="bg-white p-4 rounded-2xl flex justify-between items-center shadow-sm border border-slate-100">
                  <div>
                    <p className="text-sm font-bold text-slate-700">{day.date.split(' ').slice(0,3).join(' ')}</p>
                    <p className="text-xs text-slate-500 mt-0.5">{done}/{total} sessioni fatte</p>
                  </div>
                  <div className="text-right">
                    <p className={`font-black text-lg ${pct >= 80 ? 'text-green-500' : pct >= 50 ? 'text-amber-500' : 'text-slate-400'}`}>{pct}%</p>
                  </div>
                </div>
              );
            })}
          </div>
        </div>
      </div>
    );
  };

  return (
    <div className="bg-[#f8fafc] min-h-screen font-sans max-w-md mx-auto shadow-2xl overflow-hidden relative">
      
      {/* Modale Tutorial */}
      {showTutorial && (
        <div className="absolute inset-0 z-[100] bg-slate-900/60 backdrop-blur-sm flex items-center justify-center p-6 animate-in fade-in duration-300">
          <div className="bg-white rounded-3xl p-6 shadow-2xl w-full max-w-sm animate-in zoom-in-95 duration-500">
            <div className="w-16 h-16 bg-blue-100 rounded-full flex items-center justify-center mx-auto mb-4">
              <CheckCircle2 className="w-8 h-8 text-blue-600" />
            </div>
            <h2 className="text-2xl font-black text-center text-slate-800 mb-2">Benvenuto in PodoRehab</h2>
            <p className="text-center text-slate-600 mb-6 leading-relaxed">
              Il tuo Podologo Virtuale che ti accompagna nella guarigione. Ecco le novità:
            </p>
            
            <ul className="space-y-4 mb-8">
              <li className="flex items-start">
                <div className="bg-blue-50 p-2 rounded-lg mr-3 mt-1"><Thermometer className="w-4 h-4 text-blue-600"/></div>
                <span className="text-sm text-slate-700">Usa lo <strong>Slider del Dolore</strong> ogni giorno per monitorare l'infiammazione.</span>
              </li>
              <li className="flex items-start">
                <div className="bg-blue-50 p-2 rounded-lg mr-3 mt-1"><CheckCircle2 className="w-4 h-4 text-blue-600"/></div>
                <span className="text-sm text-slate-700">Tocca il tasto <strong>+1</strong> sulle attività che fai più volte al giorno (es. Ghiaccio). Clicca la card per i dettagli.</span>
              </li>
              <li className="flex items-start">
                <div className="bg-blue-50 p-2 rounded-lg mr-3 mt-1"><TrendingUp className="w-4 h-4 text-blue-600"/></div>
                <span className="text-sm text-slate-700">Controlla la nuova tab <strong className="mx-1">Trend</strong> per vedere i tuoi miglioramenti storici.</span>
              </li>
            </ul>
            
            <button 
              onClick={() => setShowTutorial(false)}
              className="w-full bg-blue-600 hover:bg-blue-700 text-white font-bold py-4 rounded-xl transition-colors shadow-lg shadow-blue-200"
            >
              Ho capito, iniziamo!
            </button>
          </div>
        </div>
      )}

      {/* Header Esteso */}
      <header className="bg-blue-600 text-white pt-12 pb-6 px-6 rounded-b-[2.5rem] shadow-lg relative z-10 overflow-hidden">
        <div className="absolute top-0 left-0 w-full h-full overflow-hidden pointer-events-none opacity-10">
          <div className="absolute -top-10 -right-10 w-40 h-40 bg-white rounded-full blur-3xl"></div>
          <div className="absolute bottom-0 -left-10 w-32 h-32 bg-indigo-300 rounded-full blur-2xl"></div>
        </div>

        <div className="relative flex justify-between items-center">
          <div>
            <h1 className="text-3xl font-black tracking-tight flex items-center">
              Podo<span className="text-blue-200">Rehab</span>
            </h1>
            <p className="text-blue-100 text-sm mt-1 flex items-center">
              Podologo Virtuale • Utente: SimCo
            </p>
          </div>
          <div className="flex space-x-2">
            <button 
              onClick={() => setShowTutorial(true)}
              className="w-10 h-10 bg-blue-500/50 hover:bg-blue-500 rounded-full flex items-center justify-center transition-colors"
            >
              <HelpCircle className="w-5 h-5 text-white" />
            </button>
            <div className="w-12 h-12 bg-white rounded-full flex items-center justify-center shadow-inner border-2 border-blue-100">
              <span className="text-blue-600 font-bold text-lg">SC</span>
            </div>
          </div>
        </div>
      </header>

      {/* Main Content Area */}
      <main className="p-6 pb-28 h-[calc(100vh-180px)] overflow-y-auto hide-scrollbar">
        {activeTab === 'oggi' && renderOggi()}
        {activeTab === 'protocollo' && renderProtocollo()}
        {activeTab === 'timeline' && renderTimeline()}
        {activeTab === 'trend' && renderAndamento()}
      </main>

      {/* Bottom Navigation */}
      <nav className="fixed bottom-0 w-full max-w-md bg-white border-t border-slate-100 pb-safe pt-2 px-3 flex justify-between z-50 shadow-[0_-10px_40px_-15px_rgba(0,0,0,0.1)] rounded-t-3xl">
        {[
          { id: 'oggi', icon: CheckCircle2, label: 'Oggi' },
          { id: 'protocollo', icon: FileText, label: 'Referto' },
          { id: 'timeline', icon: Calendar, label: 'Fasi' },
          { id: 'trend', icon: TrendingUp, label: 'Trend' }
        ].map((tab) => {
          const Icon = tab.icon;
          const isActive = activeTab === tab.id;
          return (
            <button 
              key={tab.id}
              onClick={() => setActiveTab(tab.id)}
              className={`flex flex-col items-center p-2 pb-5 w-1/4 transition-all duration-300 relative ${
                isActive ? 'text-blue-600 -translate-y-2' : 'text-slate-400 hover:text-slate-600'
              }`}
            >
              <div className={`p-3 rounded-2xl mb-1 transition-all duration-300 ${isActive ? 'bg-blue-50 shadow-sm' : ''}`}>
                <Icon className={`w-6 h-6 ${isActive ? 'fill-blue-100' : ''}`} />
              </div>
              <span className={`text-[10px] font-bold uppercase tracking-wider transition-opacity duration-300 ${isActive ? 'opacity-100' : 'opacity-70'}`}>
                {tab.label}
              </span>
              {isActive && <div className="absolute bottom-2 w-1.5 h-1.5 bg-blue-600 rounded-full animate-in zoom-in"></div>}
            </button>
          );
        })}
      </nav>

      {/* Global styles */}
      <style dangerouslySetInnerHTML={{__html: `
        .hide-scrollbar::-webkit-scrollbar { display: none; }
        .hide-scrollbar { -ms-overflow-style: none; scrollbar-width: none; }
        .pb-safe { padding-bottom: env(safe-area-inset-bottom, 20px); }
      `}} />
    </div>
  );
}
