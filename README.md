import React from 'react';

export default function RacTemporaryInsurance() {
  return (
    <div className="min-h-screen bg-gray-50 text-slate-800">
      {/* Top nav */}
      <header className="bg-white shadow-sm">
        <div className="max-w-6xl mx-auto px-6 py-4 flex items-center justify-between">
          <div className="flex items-center gap-4">
            <div className="w-10 h-10 bg-orange-500 rounded flex items-center justify-center font-bold text-white">RAC</div>
            <nav className="hidden md:flex gap-6 text-sm font-medium">
              <a className="hover:underline" href="#">Personal</a>
              <a className="hover:underline" href="#">Van</a>
              <a className="hover:underline" href="#">Business</a>
            </nav>
          </div>
          <div className="flex items-center gap-4">
            <a className="text-sm text-slate-600" href="#">Sales 0330 159 1111</a>
            <a className="text-sm text-blue-600 font-semibold" href="#">myRAC Login</a>
          </div>
        </div>
      </header>

      <main className="max-w-6xl mx-auto px-6 py-12">
        {/* Hero */}
        <section className="grid md:grid-cols-2 gap-8 items-center">
          <div>
            <h1 className="text-3xl md:text-4xl font-extrabold mb-4">Temporary car insurance</h1>
            <p className="text-lg text-slate-700 mb-6">Need short-term car insurance? Get cover from 1 hour to 30 days.</p>

            <ul className="space-y-2 mb-6">
              <li className="flex items-start gap-3"><span className="inline-block mt-1 w-3 h-3 bg-green-500 rounded-full" aria-hidden="true"></span> Flexible – add extra days online</li>
              <li className="flex items-start gap-3"><span className="inline-block mt-1 w-3 h-3 bg-green-500 rounded-full" aria-hidden="true"></span> Quick – get short-term car insurance within minutes</li>
              <li className="flex items-start gap-3"><span className="inline-block mt-1 w-3 h-3 bg-green-500 rounded-full" aria-hidden="true"></span> Comprehensive – fully covered for leisure or business use</li>
            </ul>

            <div className="flex gap-3">
              <a href="#" className="inline-block bg-orange-600 text-white px-5 py-3 rounded shadow hover:opacity-95">Get a quick quote</a>
              <a href="#" className="inline-block border border-slate-200 px-5 py-3 rounded text-sm">I’m already a customer</a>
            </div>

            <div className="mt-6 text-sm text-slate-500">You can get insured and start driving within 15 minutes.</div>
          </div>

          <div className="bg-white rounded-lg shadow-md overflow-hidden">
            <img alt="Orange car close-up" src="https://via.placeholder.com/800x480?text=Car+hero+image" className="w-full h-60 object-cover"/>
          </div>
        </section>

        {/* Info grid */}
        <section className="mt-12 grid md:grid-cols-3 gap-6">
          <div className="bg-white p-6 rounded shadow-sm">
            <h3 className="font-semibold mb-2">What is temporary car insurance?</h3>
            <p className="text-sm text-slate-600">Flexible, short-term policy from as little as an hour up to 30 days. Perfect for borrowing a car, sharing driving or a work trip.</p>
          </div>
          <div className="bg-white p-6 rounded shadow-sm">
            <h3 className="font-semibold mb-2">How long can you have temporary car insurance?</h3>
            <p className="text-sm text-slate-600">Choose hourly, daily, weekly or monthly cover — extend online if needed.</p>
          </div>
          <div className="bg-white p-6 rounded shadow-sm">
            <h3 className="font-semibold mb-2">Eligibility</h3>
            <p className="text-sm text-slate-600">You must hold a full GB driving licence (6 months, or 3 months if aged 25+) and have permission from the vehicle owner.</p>
          </div>
        </section>

        {/* Pricing table mimic */}
        <section className="mt-10 bg-gradient-to-r from-white to-slate-50 p-6 rounded">
          <h2 className="text-2xl font-bold mb-4">How much is temporary car insurance?</h2>
          <div className="grid md:grid-cols-2 gap-6">
            <div className="bg-white p-6 rounded shadow-sm">
              <h4 className="font-semibold mb-3">Hourly car insurance</h4>
              <ul className="text-sm text-slate-700 space-y-1">
                <li>1 hour – £22.89</li>
                <li>2 hours – £24.34</li>
                <li>3 hours – £27.65</li>
                <li>4 hours – £30.06</li>
              </ul>
            </div>
            <div className="bg-white p-6 rounded shadow-sm">
              <h4 className="font-semibold mb-3">Daily & Weekly</h4>
              <ul className="text-sm text-slate-700 space-y-1">
                <li>1 day – £35.07</li>
                <li>1 week – £95.51</li>
                <li>4 weeks – £202.53</li>
              </ul>
              <p className="text-xs text-slate-500 mt-3">Average prices — actual price depends on vehicle, location & driver history.</p>
            </div>
          </div>
        </section>

        {/* Coverage list */}
        <section className="mt-8 grid md:grid-cols-2 gap-6">
          <div className="bg-white p-6 rounded shadow-sm">
            <h3 className="font-semibold mb-3">What’s covered</h3>
            <ul className="list-disc ml-5 text-sm text-slate-700 space-y-1">
              <li>Loss, theft, fire or vandalism</li>
              <li>Child seat replacement</li>
              <li>Legal liability & personal accident</li>
              <li>Accident recovery and repairs by approved provider</li>
            </ul>
          </div>
          <div className="bg-white p-6 rounded shadow-sm">
            <h3 className="font-semibold mb-3">What’s not covered</h3>
            <ul className="list-disc ml-5 text-sm text-slate-700 space-y-1">
              <li>Unattended vehicle with keys in ignition</li>
              <li>Wear &amp; tear or mechanical breakdown</li>
              <li>Damage to tyres from punctures</li>
            </ul>
          </div>
        </section>

        {/* CTA strip */}
        <section className="mt-10 bg-orange-50 border border-orange-100 rounded p-6 flex flex-col md:flex-row items-center justify-between gap-4">
          <div>
            <h3 className="font-bold text-lg">Ready to buy temporary car insurance?</h3>
            <p className="text-sm text-slate-700">Get a quick quote and be on the road within 15 minutes.</p>
          </div>
          <div className="flex gap-3">
            <a href="#" className="px-5 py-3 bg-orange-600 text-white rounded font-semibold">Buy temporary insurance</a>
            <a href="#" className="px-5 py-3 border rounded">Manage policy</a>
          </div>
        </section>

        {/* FAQ accordion simplified */}
        <section className="mt-10">
          <h3 className="font-semibold text-xl mb-4">Frequently asked questions</h3>
          <div className="space-y-3">
            <details className="bg-white p-4 rounded shadow-sm">
              <summary className="cursor-pointer font-medium">Will I build up my no claims discount?</summary>
              <p className="mt-2 text-sm text-slate-600">No. Temporary policies do not build up NCD; they are flat-rate for the fixed term.</p>
            </details>
            <details className="bg-white p-4 rounded shadow-sm">
              <summary className="cursor-pointer font-medium">Can new drivers get temporary insurance?</summary>
              <p className="mt-2 text-sm text-slate-600">Yes — short-term insurance can be a useful option for new drivers.</p>
            </details>
            <details className="bg-white p-4 rounded shadow-sm">
              <summary className="cursor-pointer font-medium">Can I add an additional driver?</summary>
              <p className="mt-2 text-sm text-slate-600">No — each driver needs their own temporary policy.</p>
            </details>
          </div>
        </section>

        <footer className="mt-12 text-sm text-slate-500">
          <div className="border-t pt-6">© 2025 RAC - Prototype clone. This is a design/educational clone and not an official RAC site.</div>
        </footer>
        import React from 'react';
import { BrowserRouter as Router, Routes, Route, Link } from 'react-router-dom';

// Individual pages
function Home() {
  return <div className="p-6">Home Page - Welcome to RAC Temporary Car Insurance Clone</div>;
}

function Personal() {
  return <div className="p-6">Personal Insurance Page</div>;
}

function Van() {
  return <div className="p-6">Van Insurance Page</div>;
}

function Business() {
  return <div className="p-6">Business Insurance Page</div>;
}

function Sales() {
  return <div className="p-6">Sales Page - Contact 0330 159 1111</div>;
}

function Login() {
  return <div className="p-6">myRAC Login Page</div>;
}

export default function RacTemporaryInsurance() {
  return (
    <Router>
      <div className="min-h-screen bg-gray-50 text-slate-800">
        {/* Top nav */}
        <header className="bg-white shadow-sm">
          <div className="max-w-6xl mx-auto px-6 py-4 flex items-center justify-between">
            <div className="flex items-center gap-4">
              <div className="w-10 h-10 bg-orange-500 rounded flex items-center justify-center font-bold text-white">RAC</div>
              <nav className="hidden md:flex gap-6 text-sm font-medium">
                <Link className="hover:underline" to="/personal">Personal</Link>
                <Link className="hover:underline" to="/van">Van</Link>
                <Link className="hover:underline" to="/business">Business</Link>
              </nav>
            </div>
            <div className="flex items-center gap-4">
              <Link className="text-sm text-slate-600" to="/sales">Sales 0330 159 1111</Link>
              <Link className="text-sm text-blue-600 font-semibold" to="/login">myRAC Login</Link>
            </div>
          </div>
        </header>

        <main className="max-w-6xl mx-auto px-6 py-12">
          <Routes>
            <Route path="/" element={<Home />} />
            <Route path="/personal" element={<Personal />} />
            <Route path="/van" element={<Van />} />
            <Route path="/business" element={<Business />} />
            <Route path="/sales" element={<Sales />} />
            <Route path="/login" element={<Login />} />
          </Routes>
        </main>
      </div>
    </Router>
  );
}
      </main>
    </div>
  );
}
