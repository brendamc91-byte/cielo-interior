import { useState } from "react";

const mockChart = { sun: "Sol en Virgo – Casa 6", sunText: "Tu energía central busca orden y sentido. Cuando estás en equilibrio, organizas y cuidas. Cuando hay tensión, puedes exigirte de más. La guía es descansar sin culpa.", };

const mockTransit = { title: "Saturno transitando tu Casa 5", text: "Esta energía puede sentirse como menos disfrute o dudas afectivas. La invitación es madurar tu forma de amar y crear, sin apresurarte.", };

const whatIf = { text: "Cuando Marte activa la Casa 7, la energía se mueve en los vínculos. Algo necesita ser dicho con honestidad. La claridad no necesita agresión.", };

export default function App() { const [view, setView] = useState("home");

return ( <div className="min-h-screen bg-neutral-50 flex items-center justify-center p-4"> <div className="w-full max-w-md bg-white rounded-2xl shadow-lg p-6 space-y-6"> {view === "home" && ( <> <h1 className="text-2xl font-semibold text-neutral-800">Cielo Interior</h1> <p className="text-neutral-600">Hoy la energía invita a bajar el ritmo y escucharte.</p> <div className="grid gap-3"> <button onClick={() => setView("chart")} className="rounded-xl bg-neutral-800 text-white py-3">Mi carta</button> <button onClick={() => setView("transit")} className="rounded-xl bg-neutral-700 text-white py-3">Hoy en mi cielo</button> <button onClick={() => setView("whatif")} className="rounded-xl bg-neutral-600 text-white py-3">¿Qué pasa si…?</button> </div> </> )}

{view === "chart" && (
      <>
        <h2 className="text-xl font-semibold">{mockChart.sun}</h2>
        <p className="text-neutral-600">{mockChart.sunText}</p>
        <button onClick={() => setView("home")} className="text-sm text-neutral-500">Volver</button>
      </>
    )}

    {view === "transit" && (
      <>
        <h2 className="text-xl font-semibold">{mockTransit.title}</h2>
        <p className="text-neutral-600">{mockTransit.text}</p>
        <p className="italic text-neutral-500">Guía: observa sin apresurarte.</p>
        <button onClick={() => setView("home")} className="text-sm text-neutral-500">Volver</button>
      </>
    )}

    {view === "whatif" && (
      <>
        <h2 className="text-xl font-semibold">¿Qué pasa si…?</h2>
        <p className="text-neutral-600">{whatIf.text}</p>
        <button onClick={() => setView("home")} className="text-sm text-neutral-500">Volver</button>
      </>
    )}
  </div>
</div>

); }# cielo-interior
