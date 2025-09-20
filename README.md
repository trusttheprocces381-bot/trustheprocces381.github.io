
<html lang="en">
  <head>
    <meta charset="utf-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1" />
    <title>Temporary car insurance — Prototype clone</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <meta name="description" content="Temporary car insurance — short-term cover from 1 hour to 30 days. Prototype clone for educational use." />
  </head>
  <body class="min-h-screen bg-gray-50 text-slate-800">
    <!-- Top nav -->
    <header class="bg-white shadow-sm">
      <div class="max-w-6xl mx-auto px-6 py-4 flex items-center justify-between">
        <div class="flex items-center gap-4">
          <div class="w-10 h-10 bg-orange-500 rounded flex items-center justify-center font-bold text-white">RAC</div>
          <nav class="hidden md:flex gap-6 text-sm font-medium">
            <a class="hover:underline" href="#">Personal</a>
            <a class="hover:underline" href="#">Van</a>
            <a class="hover:underline" href="#">Business</a>
          </nav>
        </div>
        <div class="flex items-center gap-4">
          <a class="text-sm text-slate-600" href="#">Sales 0330 159 1111</a>
          <a class="text-sm text-blue-600 font-semibold" href="#">myRAC Login</a>
        </div>
      </div>
    </header>

    <!-- Main content -->
    <main class="max-w-6xl mx-auto px-6 py-12">
      <!-- Hero -->
      <section class="grid md:grid-cols-2 gap-8 items-center">
        <div>
          <h1 class="text-3xl md:text-4xl font-extrabold mb-4">Temporary car insurance</h1>
          <p class="text-lg text-slate-700 mb-6">Need short-term car insurance? Get cover from 1 hour to 30 days.</p>

          <ul class="space-y-2 mb-6">
            <li class="flex items-start gap-3"><span class="inline-block mt-1 w-3 h-3 bg-green-500 rounded-full" aria-hidden></span> Flexible – add extra days online</li>
            <li class="flex items-start gap-3"><span class="inline-block mt-1 w-3 h-3 bg-green-500 rounded-full" aria-hidden></span> Quick – get short-term car insurance within minutes</li>
            <li class="flex items-start gap-3"><span class="inline-block mt-1 w-3 h-3 bg-green-500 rounded-full" aria-hidden></span> Comprehensive – fully covered for leisure or business use</li>
          </ul>

          <div class="flex gap-3">
            <a href="#" class="inline-block bg-orange-600 text-white px-5 py-3 rounded shadow hover:opacity-95">Get a quick quote</a>
            <a href="#" class="inline-block border border-slate-200 px-5 py-3 rounded text-sm">I’m already a customer</a>
          </div>

          <div class="mt-6 text-sm text-slate-500">You can get insured and start driving within 15 minutes.</div>
        </div>

        <div class="bg-white rounded-lg shadow-md overflow-hidden">
          <img alt="Orange car close-up" src="https://via.placeholder.com/800x480?text=Car+hero+image" class="w-full h-60 object-cover"/>
        </div>
      </section>

      <!-- Info grid -->
      <section class="mt-12 grid md:grid-cols-3 gap-6">
        <div class="bg-white p-6 rounded shadow-sm">
          <h3 class="font-semibold mb-2">What is temporary car insurance?</h3>
          <p class="text-sm text-slate-600">Flexible, short-term policy from as little as an hour up to 30 days. Perfect for borrowing a car, sharing driving or a work trip.</p>
        </div>

        <div class="bg-white p-6 rounded shadow-sm">
          <h3 class="font-semibold mb-2">How long can you have temporary car insurance?</h3>
          <p class="text-sm text-slate-600">Choose hourly, daily, weekly or monthly cover — extend online if needed.</p>
        </div>

        <div class="bg-white p-6 rounded shadow-sm">
          <h3 class="font-semibold mb-2">Eligibility</h3>
          <p class="text-sm text-slate-600">You must hold a full GB driving licence (6 months, or 3 months if aged 25+) and have permission from the vehicle owner.</p>
        </div>
      </section>

      <!-- Pricing table mimic -->
      <section class="mt-10 bg-gradient-to-r from-white to-slate-50 p-6 rounded">
        <h2 class="text-2xl font-bold mb-4">How much is temporary car insurance?</h2>
        <div class="grid md:grid-cols-2 gap-6">
          <div class="bg-white p-6 rounded shadow-sm">
            <h4 class="font-semibold mb-3">Hourly car insurance</h4>
            <ul class="text-sm text-slate-700 space-y-1">
              <li>1 hour – £22.89</li>
              <li>2 hours – £24.34</li>
              <li>3 hours – £27.65</li>
              <li>4 hours – £30.06</li>
            </ul>
          </div>

          <div class="bg-white p-6 rounded shadow-sm">
            <h4 class="font-semibold mb-3">Daily & Weekly</h4>
            <ul class="text-sm text-slate-700 space-y-1">
              <li>1 day – £35.07</li>
              <li>1 week – £95.51</li>
              <li>4 weeks – £202.53</li>
            </ul>
            <p class="text-xs text-slate-500 mt-3">Average prices — actual price depends on vehicle, location & driver history.</p>
          </div>
        </div>
      </section>

      <!-- Coverage list -->
      <section class="mt-8 grid md:grid-cols-2 gap-6">
        <div class="bg-white p-6 rounded shadow-sm">
          <h3 class="font-semibold mb-3">What’s covered</h3>
          <ul class="list-disc ml-5 text-sm text-slate-700 space-y-1">
            <li>Loss, theft, fire or vandalism</li>
            <li>Child seat replacement</li>
            <li>Legal liability & personal accident</li>
            <li>Accident recovery and repairs by approved provider</li>
          </ul>
        </div>

        <div class="bg-white p-6 rounded shadow-sm">
          <h3 class="font-semibold mb-3">What’s not covered</h3>
          <ul class="list-disc ml-5 text-sm text-slate-700 space-y-1">
            <li>Unattended vehicle with keys in ignition</li>
            <li>Wear &amp; tear or mechanical breakdown</li>
            <li>Damage to tyres from punctures</li>
          </ul>
        </div>
      </section>

      <!-- CTA strip -->
      <section class="mt-10 bg-orange-50 border border-orange-100 rounded p-6 flex flex-col md:flex-row items-center justify-between gap-4">
        <div>
          <h3 class="font-bold text-lg">Ready to buy temporary car insurance?</h3>
          <p class="text-sm text-slate-700">Get a quick quote and be on the road within 15 minutes.</p>
        </div>
        <div class="flex gap-3">
          <a href="#" class="px-5 py-3 bg-orange-600 text-white rounded font-semibold">Buy temporary insurance</a>
          <a href="#" class="px-5 py-3 border rounded">Manage policy</a>
        </div>
      </section>

      <!-- FAQ accordion simplified -->
      <section class="mt-10">
        <h3 class="font-semibold text-xl mb-4">Frequently asked questions</h3>
        <div class="space-y-3">
          <details class="bg-white p-4 rounded shadow-sm">
            <summary class="cursor-pointer font-medium">Will I build up my no claims discount?</summary>
            <p class="mt-2 text-sm text-slate-600">No. Temporary policies do not build up NCD; they are flat-rate for the fixed term.</p>
          </details>

          <details class="bg-white p-4 rounded shadow-sm">
            <summary class="cursor-pointer font-medium">Can new drivers get temporary insurance?</summary>
            <p class="mt-2 text-sm text-slate-600">Yes — short-term insurance can be a useful option for new drivers.</p>
          </details>

          <details class="bg-white p-4 rounded shadow-sm">
            <summary class="cursor-pointer font-medium">Can I add an additional driver?</summary>
            <p class="mt-2 text-sm text-slate-600">No — each driver needs their own temporary policy.</p>
          </details>
        </div>
      </section>

      <footer class="mt-12 text-sm text-slate-500">
        <div class="border-t pt-6">© 2025 RAC - Prototype clone. This is a design/educational clone and not an official RAC site.</div>
      </footer>
    </main>
  </body>
</html>
