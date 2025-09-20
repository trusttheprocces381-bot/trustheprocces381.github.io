
Action: view_bulk --path-list /app/frontend/src/App.js,/app/frontend/src/App.css,/app/backend/server.py,/app/frontend/src/index.js
Observation: /app/frontend/src/App.js:
1|import React, { useState } from 'react';
2|import { BrowserRouter, Routes, Route, Link, useNavigate, useLocation } from 'react-router-dom';
3|import { Shield, Clock, CheckCircle, Car, FileText, Star, Phone, Mail, MapPin } from 'lucide-react';
4|import { Button } from './components/ui/button';
5|import { Card, CardContent, CardDescription, CardHeader, CardTitle } from './components/ui/card';
6|import { Input } from './components/ui/input';
7|import { Label } from './components/ui/label';
8|import { Select, SelectContent, SelectItem, SelectTrigger, SelectValue } from './components/ui/select';
9|import { Badge } from './components/ui/badge';
10|import { Separator } from './components/ui/separator';
11|import { toast } from 'sonner';
12|import axios from 'axios';
13|import './App.css';
14|
15|const BACKEND_URL = process.env.REACT_APP_BACKEND_URL;
16|const API = `${BACKEND_URL}/api`;
17|
18|// Homepage Component
19|const Homepage = () => {
20|  const navigate = useNavigate();
21|
22|  return (
23|    <div className="min-h-screen bg-gradient-to-br from-blue-50 to-indigo-100">
24|      {/* Header */}
25|      <header className="border-b bg-white/95 backdrop-blur-sm sticky top-0 z-50">
26|        <div className="container mx-auto px-4 py-4 flex items-center justify-between">
27|          <Link to="/" className="flex items-center space-x-2">
28|            <Shield className="h-8 w-8 text-blue-600" />
29|            <span className="text-2xl font-bold text-gray-900">SwiftInsure</span>
30|          </Link>
31|          <nav className="hidden md:flex space-x-8">
32|            <Link to="/" className="text-gray-700 hover:text-blue-600 font-medium">Home</Link>
33|            <Link to="/quote" className="text-gray-700 hover:text-blue-600 font-medium">Get Quote</Link>
34|            <a href="#features" className="text-gray-700 hover:text-blue-600 font-medium">Features</a>
35|            <a href="#contact" className="text-gray-700 hover:text-blue-600 font-medium">Contact</a>
36|          </nav>
37|          <Button onClick={() => navigate('/quote')} className="bg-blue-600 hover:bg-blue-700">
38|            Get Quote
39|          </Button>
40|        </div>
41|      </header>
42|
43|      {/* Hero Section */}
44|      <section className="relative py-20 overflow-hidden">
45|        <div className="absolute inset-0 bg-gradient-to-r from-blue-600/10 to-indigo-600/10"></div>
46|        <div className="container mx-auto px-4 relative">
47|          <div className="grid lg:grid-cols-2 gap-12 items-center">
48|            <div className="space-y-8">
49|              <div className="space-y-4">
50|                <Badge className="bg-blue-100 text-blue-800 border-blue-200">
51|                  <Clock className="w-4 h-4 mr-1" />
52|                  Instant Coverage
53|                </Badge>
54|                <h1 className="text-5xl font-bold text-gray-900 leading-tight">
55|                  Car Insurance That Works
56|                  <span className="text-blue-600"> When You Need It</span>
57|                </h1>
58|                <p className="text-xl text-gray-600 leading-relaxed">
59|                  Get instant quotes and temporary car insurance from just 1 hour to 28 days. 
60|                  Perfect for borrowing cars, test drives, or short-term coverage.
61|                </p>
62|              </div>
63|              
64|              <div className="flex flex-col sm:flex-row gap-4">
65|                <Button 
66|                  size="lg" 
67|                  onClick={() => navigate('/quote')}
68|                  className="text-lg px-8 py-4 bg-blue-600 hover:bg-blue-700"
69|                >
70|                  Get Instant Quote
71|                </Button>
72|                <Button 
73|                  size="lg" 
74|                  variant="outline"
75|                  className="text-lg px-8 py-4 border-2 border-gray-300 hover:border-blue-600"
76|                >
77|                  Learn More
78|                </Button>
79|              </div>
80|
81|              <div className="flex items-center space-x-8 pt-4">
82|                <div className="flex items-center space-x-2">
83|                  <CheckCircle className="w-5 h-5 text-green-500" />
84|                  <span className="text-gray-700">Instant cover</span>
85|                </div>
86|                <div className="flex items-center space-x-2">
87|                  <CheckCircle className="w-5 h-5 text-green-500" />
88|                  <span className="text-gray-700">From £2.50/hour</span>
89|                </div>
90|                <div className="flex items-center space-x-2">
91|                  <CheckCircle className="w-5 h-5 text-green-500" />
92|                  <span className="text-gray-700">5-star rated</span>
93|                </div>
94|              </div>
95|            </div>
96|
97|            <div className="relative">
98|              <div className="relative z-10">
99|                <img 
100|                  src="https://images.unsplash.com/photo-1616932321030-16411c3a6489?crop=entropy&cs=srgb&fm=jpg&ixid=M3w3NTY2Nzd8MHwxfHNlYXJjaHwxfHxtb2Rlcm4lMjBjYXJ8ZW58MHx8fHwxNzU4Mzg2NDIxfDA&ixlib=rb-4.1.0&q=85"
101|                  alt="Modern car insurance" 
102|                  className="rounded-2xl shadow-2xl w-full"
103|                />
104|              </div>
105|              <div className="absolute -bottom-4 -right-4 bg-white rounded-2xl p-6 shadow-xl z-20">
106|                <div className="flex items-center space-x-3">
107|                  <div className="flex -space-x-2">
108|                    {[1,2,3,4,5].map(i => (
109|                      <Star key={i} className="w-5 h-5 text-yellow-400 fill-current" />
110|                    ))}
111|                  </div>
112|                  <div>
113|                    <div className="text-sm font-semibold">4.9/5 Rating</div>
114|                    <div className="text-xs text-gray-500">10,000+ reviews</div>
115|                  </div>
116|                </div>
117|              </div>
118|            </div>
119|          </div>
120|        </div>
121|      </section>
122|
123|      {/* Features Section */}
124|      <section id="features" className="py-20 bg-white">
125|        <div className="container mx-auto px-4">
126|          <div className="text-center mb-16">
127|            <h2 className="text-4xl font-bold text-gray-900 mb-4">Why Choose SwiftInsure?</h2>
128|            <p className="text-xl text-gray-600 max-w-2xl mx-auto">
129|              The modern way to get car insurance. Quick, reliable, and designed for today's drivers.
130|            </p>
131|          </div>
132|
133|          <div className="grid md:grid-cols-3 gap-8">
134|            <Card className="border-0 shadow-lg hover:shadow-xl transition-shadow">
135|              <CardHeader className="text-center pb-4">
136|                <div className="mx-auto w-16 h-16 bg-blue-100 rounded-2xl flex items-center justify-center mb-4">
137|                  <Clock className="w-8 h-8 text-blue-600" />
138|                </div>
139|                <CardTitle className="text-xl">Instant Coverage</CardTitle>
140|              </CardHeader>
141|              <CardContent>
142|                <CardDescription className="text-center text-gray-600 leading-relaxed">
143|                  Get covered in minutes, not days. Our smart system provides instant quotes and immediate policy activation.
144|                </CardDescription>
145|              </CardContent>
146|            </Card>
147|
148|            <Card className="border-0 shadow-lg hover:shadow-xl transition-shadow">
149|              <CardHeader className="text-center pb-4">
150|                <div className="mx-auto w-16 h-16 bg-green-100 rounded-2xl flex items-center justify-center mb-4">
151|                  <Shield className="w-8 h-8 text-green-600" />
152|                </div>
153|                <CardTitle className="text-xl">Full Protection</CardTitle>
154|              </CardHeader>
155|              <CardContent>
156|                <CardDescription className="text-center text-gray-600 leading-relaxed">
157|                  Comprehensive coverage including third party, fire, theft, and accidental damage protection.
158|                </CardDescription>
159|              </CardContent>
160|            </Card>
161|
162|            <Card className="border-0 shadow-lg hover:shadow-xl transition-shadow">
163|              <CardHeader className="text-center pb-4">
164|                <div className="mx-auto w-16 h-16 bg-purple-100 rounded-2xl flex items-center justify-center mb-4">
165|                  <FileText className="w-8 h-8 text-purple-600" />
166|                </div>
167|                <CardTitle className="text-xl">Digital Documents</CardTitle>
168|              </CardHeader>
169|              <CardContent>
170|                <CardDescription className="text-center text-gray-600 leading-relaxed">
171|                  Instant policy documents and certificates delivered digitally. No waiting, no paperwork hassles.
172|                </CardDescription>
173|              </CardContent>
174|            </Card>
175|          </div>
176|        </div>
177|      </section>
178|
179|      {/* Contact Section */}
180|      <section id="contact" className="py-20 bg-gray-50">
181|        <div className="container mx-auto px-4">
182|          <div className="text-center mb-16">
183|            <h2 className="text-4xl font-bold text-gray-900 mb-4">Get in Touch</h2>
184|            <p className="text-xl text-gray-600">Need help? We're here for you 24/7</p>
185|          </div>
186|
187|          <div className="grid md:grid-cols-3 gap-8 max-w-4xl mx-auto">
188|            <Card className="text-center p-6">
189|              <Phone className="w-12 h-12 text-blue-600 mx-auto mb-4" />
190|              <h3 className="text-lg font-semibold mb-2">Call Us</h3>
191|              <p className="text-gray-600">0800 123 4567</p>
192|            </Card>
193|            
194|            <Card className="text-center p-6">
195|              <Mail className="w-12 h-12 text-blue-600 mx-auto mb-4" />
196|              <h3 className="text-lg font-semibold mb-2">Email Us</h3>
197|              <p className="text-gray-600">help@swiftinsure.com</p>
198|            </Card>
199|            
200|            <Card className="text-center p-6">
201|              <MapPin className="w-12 h-12 text-blue-600 mx-auto mb-4" />
202|              <h3 className="text-lg font-semibold mb-2">Visit Us</h3>
203|              <p className="text-gray-600">London, UK</p>
204|            </Card>
205|          </div>
206|        </div>
207|      </section>
208|
209|      {/* Footer */}
210|      <footer className="bg-gray-900 text-white py-12">
211|        <div className="container mx-auto px-4">
212|          <div className="flex flex-col md:flex-row justify-between items-center">
213|            <div className="flex items-center space-x-2 mb-4 md:mb-0">
214|              <Shield className="h-8 w-8 text-blue-400" />
215|              <span className="text-2xl font-bold">SwiftInsure</span>
216|            </div>
217|            <p className="text-gray-400">© 2024 SwiftInsure. All rights reserved.</p>
218|          </div>
219|        </div>
220|      </footer>
221|    </div>
222|  );
223|};
224|
225|// Quote Form Component
226|const QuoteForm = () => {
227|  const navigate = useNavigate();
228|  const [formData, setFormData] = useState({
229|    // Vehicle details
230|    registration: '',
231|    make: '',
232|    model: '',
233|    year: '',
234|    
235|    // Driver details
236|    firstName: '',
237|    lastName: '',
238|    email: '',
239|    dateOfBirth: '',
240|    licenseYears: '',
241|    
242|    // Coverage details
243|    coverageType: '',
244|    duration: '',
245|    startDate: ''
246|  });
247|
248|  const [currentStep, setCurrentStep] = useState(1);
249|  const [isLoading, setIsLoading] = useState(false);
250|
251|  const handleInputChange = (field, value) => {
252|    setFormData(prev => ({ ...prev, [field]: value }));
253|  };
254|
255|  const handleNext = () => {
256|    if (currentStep < 3) {
257|      setCurrentStep(currentStep + 1);
258|    }
259|  };
260|
261|  const handleBack = () => {
262|    if (currentStep > 1) {
263|      setCurrentStep(currentStep - 1);
264|    }
265|  };
266|
267|  const handleSubmit = async () => {
268|    setIsLoading(true);
269|    try {
270|      const response = await axios.post(`${API}/quote`, formData);
271|      navigate('/quote-result', { state: { quote: response.data, formData } });
272|      toast.success('Quote generated successfully!');
273|    } catch (error) {
274|      console.error('Error generating quote:', error);
275|      toast.error('Failed to generate quote. Please try again.');
276|    } finally {
277|      setIsLoading(false);
278|    }
279|  };
280|
281|  return (
282|    <div className="min-h-screen bg-gradient-to-br from-blue-50 to-indigo-100">
283|      {/* Header */}
284|      <header className="border-b bg-white/95 backdrop-blur-sm">
285|        <div className="container mx-auto px-4 py-4 flex items-center justify-between">
286|          <Link to="/" className="flex items-center space-x-2">
287|            <Shield className="h-8 w-8 text-blue-600" />
288|            <span className="text-2xl font-bold text-gray-900">SwiftInsure</span>
289|          </Link>
290|          <Button variant="outline" onClick={() => navigate('/')}>
291|            Back to Home
292|          </Button>
293|        </div>
294|      </header>
295|
296|      <div className="container mx-auto px-4 py-12">
297|        <div className="max-w-2xl mx-auto">
298|          <div className="mb-8">
299|            <h1 className="text-3xl font-bold text-gray-900 mb-2">Get Your Quote</h1>
300|            <p className="text-gray-600">Fill in your details to get an instant car insurance quote</p>
301|          </div>
302|
303|          {/* Progress Bar */}
304|          <div className="mb-8">
305|            <div className="flex items-center space-x-4">
306|              {[1, 2, 3].map((step) => (
307|                <div key={step} className="flex items-center">
308|                  <div className={`w-8 h-8 rounded-full flex items-center justify-center text-sm font-medium ${
309|                    step <= currentStep ? 'bg-blue-600 text-white' : 'bg-gray-200 text-gray-500'
310|                  }`}>
311|                    {step}
312|                  </div>
313|                  {step < 3 && (
314|                    <div className={`w-16 h-1 ml-4 ${
315|                      step < currentStep ? 'bg-blue-600' : 'bg-gray-200'
316|                    }`} />
317|                  )}
318|                </div>
319|              ))}
320|            </div>
321|            <div className="flex justify-between mt-2 text-sm text-gray-600">
322|              <span>Vehicle Details</span>
323|              <span>Driver Details</span>
324|              <span>Coverage Options</span>
325|            </div>
326|          </div>
327|
328|          <Card>
329|            <CardContent className="p-8">
330|              {/* Step 1: Vehicle Details */}
331|              {currentStep === 1 && (
332|                <div className="space-y-6">
333|                  <h2 className="text-xl font-semibold text-gray-900 mb-4">Vehicle Details</h2>
334|                  
335|                  <div className="grid md:grid-cols-2 gap-4">
336|                    <div>
337|                      <Label htmlFor="registration">Registration Number</Label>
338|                      <Input
339|                        id="registration"
340|                        placeholder="e.g. AB12 CDE"
341|                        value={formData.registration}
342|                        onChange={(e) => handleInputChange('registration', e.target.value)}
343|                        className="mt-1"
344|                      />
345|                    </div>
346|                    
347|                    <div>
348|                      <Label htmlFor="make">Make</Label>
349|                      <Select onValueChange={(value) => handleInputChange('make', value)}>
350|                        <SelectTrigger className="mt-1">
351|                          <SelectValue placeholder="Select make" />
352|                        </SelectTrigger>
353|                        <SelectContent>
354|                          <SelectItem value="audi">Audi</SelectItem>
355|                          <SelectItem value="bmw">BMW</SelectItem>
356|                          <SelectItem value="ford">Ford</SelectItem>
357|                          <SelectItem value="mercedes">Mercedes</SelectItem>
358|                          <SelectItem value="volkswagen">Volkswagen</SelectItem>
359|                          <SelectItem value="toyota">Toyota</SelectItem>
360|                          <SelectItem value="other">Other</SelectItem>
361|                        </SelectContent>
362|                      </Select>
363|                    </div>
364|                  </div>
365|
366|                  <div className="grid md:grid-cols-2 gap-4">
367|                    <div>
368|                      <Label htmlFor="model">Model</Label>
369|                      <Input
370|                        id="model"
371|                        placeholder="e.g. Golf"
372|                        value={formData.model}
373|                        onChange={(e) => handleInputChange('model', e.target.value)}
374|                        className="mt-1"
375|                      />
376|                    </div>
377|                    
378|                    <div>
379|                      <Label htmlFor="year">Year</Label>
380|                      <Select onValueChange={(value) => handleInputChange('year', value)}>
381|                        <SelectTrigger className="mt-1">
382|                          <SelectValue placeholder="Select year" />
383|                        </SelectTrigger>
384|                        <SelectContent>
385|                          {Array.from({ length: 25 }, (_, i) => 2024 - i).map(year => (
386|                            <SelectItem key={year} value={year.toString()}>{year}</SelectItem>
387|                          ))}
388|                        </SelectContent>
389|                      </Select>
390|                    </div>
391|                  </div>
392|                </div>
393|              )}
394|
395|              {/* Step 2: Driver Details */}
396|              {currentStep === 2 && (
397|                <div className="space-y-6">
398|                  <h2 className="text-xl font-semibold text-gray-900 mb-4">Driver Details</h2>
399|                  
400|                  <div className="grid md:grid-cols-2 gap-4">
401|                    <div>
402|                      <Label htmlFor="firstName">First Name</Label>
403|                      <Input
404|                        id="firstName"
405|                        placeholder="John"
406|                        value={formData.firstName}
407|                        onChange={(e) => handleInputChange('firstName', e.target.value)}
408|                        className="mt-1"
409|                      />
410|                    </div>
411|                    
412|                    <div>
413|                      <Label htmlFor="lastName">Last Name</Label>
414|                      <Input
415|                        id="lastName"
416|                        placeholder="Smith"
417|                        value={formData.lastName}
418|                        onChange={(e) => handleInputChange('lastName', e.target.value)}
419|                        className="mt-1"
420|                      />
421|                    </div>
422|                  </div>
423|
424|                  <div>
425|                    <Label htmlFor="email">Email Address</Label>
426|                    <Input
427|                      id="email"
428|                      type="email"
429|                      placeholder="john@example.com"
430|                      value={formData.email}
431|                      onChange={(e) => handleInputChange('email', e.target.value)}
432|                      className="mt-1"
433|                    />
434|                  </div>
435|
436|                  <div className="grid md:grid-cols-2 gap-4">
437|                    <div>
438|                      <Label htmlFor="dateOfBirth">Date of Birth</Label>
439|                      <Input
440|                        id="dateOfBirth"
441|                        type="date"
442|                        value={formData.dateOfBirth}
443|                        onChange={(e) => handleInputChange('dateOfBirth', e.target.value)}
444|                        className="mt-1"
445|                      />
446|                    </div>
447|                    
448|                    <div>
449|                      <Label htmlFor="licenseYears">Years with License</Label>
450|                      <Select onValueChange={(value) => handleInputChange('licenseYears', value)}>
451|                        <SelectTrigger className="mt-1">
452|                          <SelectValue placeholder="Select years" />
453|                        </SelectTrigger>
454|                        <SelectContent>
455|                          <SelectItem value="0-1">0-1 years</SelectItem>
456|                          <SelectItem value="1-3">1-3 years</SelectItem>
457|                          <SelectItem value="3-5">3-5 years</SelectItem>
458|                          <SelectItem value="5-10">5-10 years</SelectItem>
459|                          <SelectItem value="10+">10+ years</SelectItem>
460|                        </SelectContent>
461|                      </Select>
462|                    </div>
463|                  </div>
464|                </div>
465|              )}
466|
467|              {/* Step 3: Coverage Options */}
468|              {currentStep === 3 && (
469|                <div className="space-y-6">
470|                  <h2 className="text-xl font-semibold text-gray-900 mb-4">Coverage Options</h2>
471|                  
472|                  <div>
473|                    <Label htmlFor="coverageType">Coverage Type</Label>
474|                    <Select onValueChange={(value) => handleInputChange('coverageType', value)}>
475|                      <SelectTrigger className="mt-1">
476|                        <SelectValue placeholder="Select coverage" />
477|                      </SelectTrigger>
478|                      <SelectContent>
479|                        <SelectItem value="comprehensive">Comprehensive</SelectItem>
480|                        <SelectItem value="third-party">Third Party Only</SelectItem>
481|                        <SelectItem value="third-party-theft">Third Party, Fire & Theft</SelectItem>
482|                      </SelectContent>
483|                    </Select>
484|                  </div>
485|
486|                  <div className="grid md:grid-cols-2 gap-4">
487|                    <div>
488|                      <Label htmlFor="duration">Duration</Label>
489|                      <Select onValueChange={(value) => handleInputChange('duration', value)}>
490|                        <SelectTrigger className="mt-1">
491|                          <SelectValue placeholder="Select duration" />
492|                        </SelectTrigger>
493|                        <SelectContent>
494|                          <SelectItem value="1-day">1 Day</SelectItem>
495|                          <SelectItem value="3-days">3 Days</SelectItem>
496|                          <SelectItem value="1-week">1 Week</SelectItem>
497|                          <SelectItem value="2-weeks">2 Weeks</SelectItem>
498|                          <SelectItem value="1-month">1 Month</SelectItem>
499|                        </SelectContent>
500|                      </Select>
501|                    </div>
502|                    
503|                    <div>
504|                      <Label htmlFor="startDate">Start Date</Label>
505|                      <Input
506|                        id="startDate"
507|                        type="date"
508|                        value={formData.startDate}
509|                        onChange={(e) => handleInputChange('startDate', e.target.value)}
510|                        className="mt-1"
511|                        min={new Date().toISOString().split('T')[0]}
512|                      />
513|                    </div>
514|                  </div>
515|                </div>
516|              )}
517|
518|              {/* Navigation Buttons */}
519|              <div className="flex justify-between mt-8 pt-6 border-t">
520|                {currentStep > 1 && (
521|                  <Button variant="outline" onClick={handleBack}>
522|                    Back
523|                  </Button>
524|                )}
525|                
526|                {currentStep < 3 ? (
527|                  <Button onClick={handleNext} className="ml-auto">
528|                    Next
529|                  </Button>
530|                ) : (
531|                  <Button 
532|                    onClick={handleSubmit} 
533|                    disabled={isLoading}
534|                    className="ml-auto"
535|                  >
536|                    {isLoading ? 'Generating Quote...' : 'Get Quote'}
537|                  </Button>
538|                )}
539|              </div>
540|            </CardContent>
541|          </Card>
542|        </div>
543|      </div>
544|    </div>
545|  );
546|};
547|
548|// Quote Result Component
549|const QuoteResult = () => {
550|  const navigate = useNavigate();
551|  const location = useLocation();
552|  const quote = location.state?.quote;
553|  const formData = location.state?.formData;
554|
555|  const handlePurchase = async () => {
556|    try {
557|      const response = await axios.post(`${API}/purchase`, {
558|        quoteId: quote.id,
559|        formData: formData
560|      });
561|      
562|      navigate('/policy-document', { 
563|        state: { 
564|          policy: response.data,
565|          formData: formData,
566|          quote: quote
567|        } 
568|      });
569|      toast.success('Policy purchased successfully!');
570|    } catch (error) {
571|      console.error('Error purchasing policy:', error);
572|      toast.error('Failed to purchase policy. Please try again.');
573|    }
574|  };
575|
576|  if (!quote) {
577|    return (
578|      <div className="min-h-screen flex items-center justify-center">
579|        <div className="text-center">
580|          <h2 className="text-xl font-semibold mb-2">No Quote Found</h2>
581|          <Button onClick={() => navigate('/quote')}>Get a Quote</Button>
582|        </div>
583|      </div>
584|    );
585|  }
586|
587|  return (
588|    <div className="min-h-screen bg-gradient-to-br from-blue-50 to-indigo-100">
589|      {/* Header */}
590|      <header className="border-b bg-white/95 backdrop-blur-sm">
591|        <div className="container mx-auto px-4 py-4 flex items-center justify-between">
592|          <Link to="/" className="flex items-center space-x-2">
593|            <Shield className="h-8 w-8 text-blue-600" />
594|            <span className="text-2xl font-bold text-gray-900">SwiftInsure</span>
595|          </Link>
596|          <Button variant="outline" onClick={() => navigate('/quote')}>
597|            New Quote
598|          </Button>
599|        </div>
600|      </header>
601|
602|      <div className="container mx-auto px-4 py-12">
603|        <div className="max-w-4xl mx-auto">
604|          <div className="mb-8">
605|            <h1 className="text-3xl font-bold text-gray-900 mb-2">Your Quote</h1>
606|            <p className="text-gray-600">Review your quote details and purchase your policy</p>
607|          </div>
608|
609|          <div className="grid lg:grid-cols-3 gap-8">
610|            {/* Quote Details */}
611|            <div className="lg:col-span-2 space-y-6">
612|              <Card>
613|                <CardHeader>
614|                  <CardTitle className="flex items-center">
615|                    <Car className="w-5 h-5 mr-2" />
616|                    Vehicle & Driver Details
617|                  </CardTitle>
618|                </CardHeader>
619|                <CardContent className="space-y-4">
620|                  <div className="grid md:grid-cols-2 gap-4">
621|                    <div>
622|                      <p className="text-sm text-gray-500">Vehicle</p>
623|                      <p className="font-medium">{formData?.make} {formData?.model} ({formData?.year})</p>
624|                      <p className="text-sm text-gray-600">{formData?.registration}</p>
625|                    </div>
626|                    <div>
627|                      <p className="text-sm text-gray-500">Driver</p>
628|                      <p className="font-medium">{formData?.firstName} {formData?.lastName}</p>
629|                      <p className="text-sm text-gray-600">{formData?.licenseYears} driving experience</p>
630|                    </div>
631|                  </div>
632|                  
633|                  <Separator />
634|                  
635|                  <div className="grid md:grid-cols-2 gap-4">
636|                    <div>
637|                      <p className="text-sm text-gray-500">Coverage</p>
638|                      <p className="font-medium capitalize">{formData?.coverageType?.replace('-', ' ')}</p>
639|                    </div>
640|                    <div>
641|                      <p className="text-sm text-gray-500">Duration</p>
642|                      <p className="font-medium">{formData?.duration?.replace('-', ' ')}</p>
643|                      <p className="text-sm text-gray-600">Starting {formData?.startDate}</p>
644|                    </div>
645|                  </div>
646|                </CardContent>
647|              </Card>
648|
649|              <Card>
650|                <CardHeader>
651|                  <CardTitle>What's Included</CardTitle>
652|                </CardHeader>
653|                <CardContent>
654|                  <div className="space-y-3">
655|                    <div className="flex items-center space-x-3">
656|                      <CheckCircle className="w-5 h-5 text-green-500" />
657|                      <span>Third party liability cover</span>
658|                    </div>
659|                    <div className="flex items-center space-x-3">
660|                      <CheckCircle className="w-5 h-5 text-green-500" />
661|                      <span>Fire and theft protection</span>
662|                    </div>
663|                    <div className="flex items-center space-x-3">
664|                      <CheckCircle className="w-5 h-5 text-green-500" />
665|                      <span>Windscreen cover</span>
666|                    </div>
667|                    <div className="flex items-center space-x-3">
668|                      <CheckCircle className="w-5 h-5 text-green-500" />
669|                      <span>24/7 customer support</span>
670|                    </div>
671|                    <div className="flex items-center space-x-3">
672|                      <CheckCircle className="w-5 h-5 text-green-500" />
673|                      <span>Instant policy documents</span>
674|                    </div>
675|                  </div>
676|                </CardContent>
677|              </Card>
678|            </div>
679|
680|            {/* Quote Summary */}
681|            <div>
682|              <Card className="sticky top-8">
683|                <CardHeader>
684|                  <CardTitle className="text-center">Quote Summary</CardTitle>
685|                </CardHeader>
686|                <CardContent className="space-y-6">
687|                  <div className="text-center">
688|                    <div className="text-4xl font-bold text-blue-600">£{quote.price}</div>
689|                    <p className="text-gray-600">{formData?.duration?.replace('-', ' ')}</p>
690|                  </div>
691|
692|                  <Separator />
693|
694|                  <div className="space-y-2">
695|                    <div className="flex justify-between">
696|                      <span className="text-gray-600">Base premium</span>
697|                      <span>£{quote.basePremium}</span>
698|                    </div>
699|                    <div className="flex justify-between">
700|                      <span className="text-gray-600">Insurance tax</span>
701|                      <span>£{quote.tax}</span>
702|                    </div>
703|                    <div className="flex justify-between font-semibold">
704|                      <span>Total</span>
705|                      <span>£{quote.price}</span>
706|                    </div>
707|                  </div>
708|
709|                  <Button 
710|                    onClick={handlePurchase}
711|                    className="w-full"
712|                    size="lg"
713|                  >
714|                    Buy Now
715|                  </Button>
716|
717|                  <div className="text-center">
718|                    <p className="text-xs text-gray-500">
719|                      Instant cover starts from your selected date
720|                    </p>
721|                  </div>
722|                </CardContent>
723|              </Card>
724|            </div>
725|          </div>
726|        </div>
727|      </div>
728|    </div>
729|  );
730|};
731|
732|// Policy Document Component
733|const PolicyDocument = () => {
734|  const navigate = useNavigate();
735|  const location = useLocation();
736|  const policy = location.state?.policy;
737|  const formData = location.state?.formData;
738|  const quote = location.state?.quote;
739|
740|  if (!policy) {
741|    return (
742|      <div className="min-h-screen flex items-center justify-center">
743|        <div className="text-center">
744|          <h2 className="text-xl font-semibold mb-2">No Policy Found</h2>
745|          <Button onClick={() => navigate('/')}>Go Home</Button>
746|        </div>
747|      </div>
748|    );
749|  }
750|
751|  return (
752|    <div className="min-h-screen bg-gradient-to-br from-blue-50 to-indigo-100">
753|      {/* Header */}
754|      <header className="border-b bg-white/95 backdrop-blur-sm">
755|        <div className="container mx-auto px-4 py-4 flex items-center justify-between">
756|          <Link to="/" className="flex items-center space-x-2">
757|            <Shield className="h-8 w-8 text-blue-600" />
758|            <span className="text-2xl font-bold text-gray-900">SwiftInsure</span>
759|          </Link>
760|          <Button variant="outline" onClick={() => navigate('/')}>
761|            Home
762|          </Button>
763|        </div>
764|      </header>
765|
766|      <div className="container mx-auto px-4 py-12">
767|        <div className="max-w-4xl mx-auto">
768|          <div className="mb-8 text-center">
769|            <div className="w-16 h-16 bg-green-100 rounded-full flex items-center justify-center mx-auto mb-4">
770|              <CheckCircle className="w-8 h-8 text-green-600" />
771|            </div>
772|            <h1 className="text-3xl font-bold text-gray-900 mb-2">Policy Purchased Successfully!</h1>
773|            <p className="text-gray-600">Your insurance is now active. Keep this document for your records.</p>
774|          </div>
775|
776|          <Card className="mb-8">
777|            <CardHeader className="bg-blue-600 text-white">
778|              <CardTitle className="text-center text-2xl">Insurance Policy Certificate</CardTitle>
779|              <CardDescription className="text-center text-blue-100">
780|                Policy Number: {policy.policyNumber}
781|              </CardDescription>
782|            </CardHeader>
783|            <CardContent className="p-8 space-y-6">
784|              {/* Policy Holder Details */}
785|              <div>
786|                <h3 className="text-lg font-semibold mb-3 text-gray-900">Policy Holder</h3>
787|                <div className="grid md:grid-cols-2 gap-4">
788|                  <div>
789|                    <p className="text-sm text-gray-500">Name</p>
790|                    <p className="font-medium">{formData?.firstName} {formData?.lastName}</p>
791|                  </div>
792|                  <div>
793|                    <p className="text-sm text-gray-500">Email</p>
794|                    <p className="font-medium">{formData?.email}</p>
795|                  </div>
796|                </div>
797|              </div>
798|
799|              <Separator />
800|
801|              {/* Vehicle Details */}
802|              <div>
803|                <h3 className="text-lg font-semibold mb-3 text-gray-900">Vehicle Details</h3>
804|                <div className="grid md:grid-cols-3 gap-4">
805|                  <div>
806|                    <p className="text-sm text-gray-500">Make & Model</p>
807|                    <p className="font-medium">{formData?.make} {formData?.model}</p>
808|                  </div>
809|                  <div>
810|                    <p className="text-sm text-gray-500">Year</p>
811|                    <p className="font-medium">{formData?.year}</p>
812|                  </div>
813|                  <div>
814|                    <p className="text-sm text-gray-500">Registration</p>
815|                    <p className="font-medium">{formData?.registration}</p>
816|                  </div>
817|                </div>
818|              </div>
819|
820|              <Separator />
821|
822|              {/* Coverage Details */}
823|              <div>
824|                <h3 className="text-lg font-semibold mb-3 text-gray-900">Coverage Details</h3>
825|                <div className="grid md:grid-cols-3 gap-4">
826|                  <div>
827|                    <p className="text-sm text-gray-500">Coverage Type</p>
828|                    <p className="font-medium capitalize">{formData?.coverageType?.replace('-', ' ')}</p>
829|                  </div>
830|                  <div>
831|                    <p className="text-sm text-gray-500">Duration</p>
832|                    <p className="font-medium">{formData?.duration?.replace('-', ' ')}</p>
833|                  </div>
834|                  <div>
835|                    <p className="text-sm text-gray-500">Premium</p>
836|                    <p className="font-medium">£{quote?.price}</p>
837|                  </div>
838|                </div>
839|              </div>
840|
841|              <Separator />
842|
843|              {/* Policy Dates */}
844|              <div>
845|                <h3 className="text-lg font-semibold mb-3 text-gray-900">Policy Period</h3>
846|                <div className="grid md:grid-cols-2 gap-4">
847|                  <div>
848|                    <p className="text-sm text-gray-500">Start Date</p>
849|                    <p className="font-medium">{policy.startDate}</p>
850|                  </div>
851|                  <div>
852|                    <p className="text-sm text-gray-500">End Date</p>
853|                    <p className="font-medium">{policy.endDate}</p>
854|                  </div>
855|                </div>
856|              </div>
857|
858|              <Separator />
859|
860|              {/* Important Information */}
861|              <div>
862|                <h3 className="text-lg font-semibold mb-3 text-gray-900">Important Information</h3>
863|                <div className="bg-yellow-50 border border-yellow-200 rounded-lg p-4">
864|                  <ul className="text-sm space-y-1 text-gray-700">
865|                    <li>• Keep this certificate with you when driving</li>
866|                    <li>• This policy covers the vehicle and named driver only</li>
867|                    <li>• Policy is valid for the dates and times specified</li>
868|                    <li>• Contact us immediately if you need to make a claim</li>
869|                  </ul>
870|                </div>
871|              </div>
872|
873|              {/* Digital Signature */}
874|              <div className="text-center pt-6">
875|                <p className="text-sm text-gray-500">This is a digitally issued policy certificate</p>
876|                <p className="text-xs text-gray-400">Generated on {new Date().toLocaleDateString()}</p>
877|              </div>
878|            </CardContent>
879|          </Card>
880|
881|          <div className="text-center">
882|            <Button onClick={() => navigate('/')} size="lg">
883|              Return to Homepage
884|            </Button>
885|          </div>
886|        </div>
887|      </div>
888|    </div>
889|  );
890|};
891|
892|// Main App Component
893|function App() {
894|  return (
895|    <div className="App">
896|      <BrowserRouter>
897|        <Routes>
898|          <Route path="/" element={<Homepage />} />
899|          <Route path="/quote" element={<QuoteForm />} />
900|          <Route path="/quote-result" element={<QuoteResult />} />
901|          <Route path="/policy-document" element={<PolicyDocument />} />
902|        </Routes>
903|      </BrowserRouter>
904|    </div>
905|  );
906|}
907|
908|export default App;


/app/frontend/src/App.css:
1|@import url('https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700;800&display=swap');
2|
3|* {
4|  margin: 0;
5|  padding: 0;
6|  box-sizing: border-box;
7|}
8|
9|body {
10|  font-family: 'Inter', -apple-system, BlinkMacSystemFont, 'Segoe UI', 'Roboto', 'Oxygen',
11|    'Ubuntu', 'Cantarell', 'Fira Sans', 'Droid Sans', 'Helvetica Neue',
12|    sans-serif;
13|  -webkit-font-smoothing: antialiased;
14|  -moz-osx-font-smoothing: grayscale;
15|  background-color: #fafafa;
16|}
17|
18|.App {
19|  min-height: 100vh;
20|}
21|
22|/* Custom scrollbar */
23|::-webkit-scrollbar {
24|  width: 6px;
25|}
26|
27|::-webkit-scrollbar-track {
28|  background: #f1f1f1;
29|}
30|
31|::-webkit-scrollbar-thumb {
32|  background: #c1c1c1;
33|  border-radius: 3px;
34|}
35|
36|::-webkit-scrollbar-thumb:hover {
37|  background: #a8a8a8;
38|}
39|
40|/* Smooth transitions for interactive elements */
41|button {
42|  transition: background-color 0.2s ease, transform 0.1s ease, box-shadow 0.2s ease;
43|}
44|
45|button:hover {
46|  transform: translateY(-1px);
47|}
48|
49|button:active {
50|  transform: translateY(0);
51|}
52|
53|/* Card hover effects */
54|.card-hover {
55|  transition: transform 0.2s ease, box-shadow 0.2s ease;
56|}
57|
58|.card-hover:hover {
59|  transform: translateY(-2px);
60|  box-shadow: 0 10px 25px rgba(0, 0, 0, 0.1);
61|}
62|
63|/* Custom focus styles */
64|input:focus,
65|select:focus,
66|textarea:focus {
67|  outline: none;
68|  ring: 2px;
69|  ring-color: #3b82f6;
70|  ring-offset: 2px;
71|}
72|
73|/* Gradient text */
74|.gradient-text {
75|  background: linear-gradient(135deg, #3b82f6, #8b5cf6);
76|  -webkit-background-clip: text;
77|  -webkit-text-fill-color: transparent;
78|  background-clip: text;
79|}
80|
81|/* Hero section animations */
82|@keyframes fadeInUp {
83|  from {
84|    opacity: 0;
85|    transform: translateY(30px);
86|  }
87|  to {
88|    opacity: 1;
89|    transform: translateY(0);
90|  }
91|}
92|
93|.animate-fade-in-up {
94|  animation: fadeInUp 0.6s ease-out;
95|}
96|
97|/* Loading spinner */
98|@keyframes spin {
99|  to {
100|    transform: rotate(360deg);
101|  }
102|}
103|
104|.animate-spin {
105|  animation: spin 1s linear infinite;
106|}
107|
108|/* Glass morphism effect */
109|.glass-morphism {
110|  background: rgba(255, 255, 255, 0.25);
111|  backdrop-filter: blur(10px);
112|  border: 1px solid rgba(255, 255, 255, 0.18);
113|}
114|
115|/* Progress bar animation */
116|@keyframes progressFill {
117|  from {
118|    width: 0%;
119|  }
120|  to {
121|    width: 100%;
122|  }
123|}
124|
125|.progress-fill {
126|  animation: progressFill 0.5s ease-out;
127|}
128|
129|/* Status indicators */
130|.status-active {
131|  position: relative;
132|}
133|
134|.status-active::before {
135|  content: '';
136|  position: absolute;
137|  width: 8px;
138|  height: 8px;
139|  background-color: #10b981;
140|  border-radius: 50%;
141|  top: -2px;
142|  right: -2px;
143|  animation: pulse 2s infinite;
144|}
145|
146|@keyframes pulse {
147|  0%, 100% {
148|    opacity: 1;
149|  }
150|  50% {
151|    opacity: 0.5;
152|  }
153|}
154|
155|/* Mobile responsiveness improvements */
156|@media (max-width: 768px) {
157|  .container {
158|    padding-left: 1rem;
159|    padding-right: 1rem;
160|  }
161|  
162|  h1 {
163|    font-size: 2.5rem;
164|  }
165|  
166|  h2 {
167|    font-size: 2rem;
168|  }
169|  
170|  .text-5xl {
171|    font-size: 2.5rem;
172|  }
173|  
174|  .text-4xl {
175|    font-size: 2rem;
176|  }
177|}
178|
179|/* Print styles for policy documents */
180|@media print {
181|  .no-print {
182|    display: none !important;
183|  }
184|  
185|  body {
186|    background: white !important;
187|    color: black !important;
188|  }
189|  
190|  .container {
191|    max-width: none !important;
192|    margin: 0 !important;
193|    padding: 0 !important;
194|  }
195|}
196|
197|/* Custom selection */
198|::selection {
199|  background-color: #3b82f6;
200|  color: white;
201|}
202|
203|/* High contrast mode support */
204|@media (prefers-contrast: high) {
205|  button {
206|    border: 2px solid;
207|  }
208|  
209|  .card {
210|    border: 2px solid #000;
211|  }
212|}


/app/backend/server.py:
1|from fastapi import FastAPI, APIRouter, HTTPException
2|from dotenv import load_dotenv
3|from starlette.middleware.cors import CORSMiddleware
4|from motor.motor_asyncio import AsyncIOMotorClient
5|import os
6|import logging
7|from pathlib import Path
8|from pydantic import BaseModel, Field
9|from typing import List, Optional
10|import uuid
11|from datetime import datetime, timezone, timedelta
12|import random
13|
14|ROOT_DIR = Path(__file__).parent
15|load_dotenv(ROOT_DIR / '.env')
16|
17|# MongoDB connection
18|mongo_url = os.environ['MONGO_URL']
19|client = AsyncIOMotorClient(mongo_url)
20|db = client[os.environ['DB_NAME']]
21|
22|# Create the main app without a prefix
23|app = FastAPI()
24|
25|# Create a router with the /api prefix
26|api_router = APIRouter(prefix="/api")
27|
28|# Define Models
29|class QuoteRequest(BaseModel):
30|    # Vehicle details
31|    registration: str
32|    make: str
33|    model: str
34|    year: str
35|    
36|    # Driver details
37|    firstName: str
38|    lastName: str
39|    email: str
40|    dateOfBirth: str
41|    licenseYears: str
42|    
43|    # Coverage details
44|    coverageType: str
45|    duration: str
46|    startDate: str
47|
48|class Quote(BaseModel):
49|    id: str = Field(default_factory=lambda: str(uuid.uuid4()))
50|    price: float
51|    basePremium: float
52|    tax: float
53|    validUntil: str
54|    created_at: datetime = Field(default_factory=lambda: datetime.now(timezone.utc))
55|
56|class PurchaseRequest(BaseModel):
57|    quoteId: str
58|    formData: QuoteRequest
59|
60|class Policy(BaseModel):
61|    id: str = Field(default_factory=lambda: str(uuid.uuid4()))
62|    policyNumber: str
63|    startDate: str
64|    endDate: str
65|    premium: float
66|    status: str = "active"
67|    created_at: datetime = Field(default_factory=lambda: datetime.now(timezone.utc))
68|
69|# Utility functions
70|def calculate_quote_price(quote_data: QuoteRequest) -> dict:
71|    """Calculate insurance quote based on provided data"""
72|    base_price = 25.0  # Base price
73|    
74|    # Duration multipliers
75|    duration_multipliers = {
76|        "1-day": 1.0,
77|        "3-days": 2.5,
78|        "1-week": 4.0,
79|        "2-weeks": 6.5,
80|        "1-month": 10.0
81|    }
82|    
83|    # Coverage type multipliers
84|    coverage_multipliers = {
85|        "third-party": 1.0,
86|        "third-party-theft": 1.3,
87|        "comprehensive": 1.6
88|    }
89|    
90|    # License experience discount
91|    license_discounts = {
92|        "0-1": 1.5,  # Higher risk
93|        "1-3": 1.2,
94|        "3-5": 1.0,
95|        "5-10": 0.9,
96|        "10+": 0.8   # Lower risk
97|    }
98|    
99|    # Vehicle age factor
100|    current_year = datetime.now().year
101|    vehicle_age = current_year - int(quote_data.year)
102|    age_factor = 1.0 + (vehicle_age * 0.02)  # 2% increase per year
103|    
104|    # Calculate base premium
105|    duration_factor = duration_multipliers.get(quote_data.duration, 1.0)
106|    coverage_factor = coverage_multipliers.get(quote_data.coverageType, 1.0)
107|    license_factor = license_discounts.get(quote_data.licenseYears, 1.0)
108|    
109|    base_premium = base_price * duration_factor * coverage_factor * license_factor * age_factor
110|    
111|    # Add some randomness for realistic variation
112|    variation = random.uniform(0.9, 1.1)
113|    base_premium = base_premium * variation
114|    
115|    # Round to 2 decimal places
116|    base_premium = round(base_premium, 2)
117|    
118|    # Calculate tax (12% insurance premium tax in UK)
119|    tax = round(base_premium * 0.12, 2)
120|    
121|    # Total price
122|    total_price = round(base_premium + tax, 2)
123|    
124|    return {
125|        "basePremium": base_premium,
126|        "tax": tax,
127|        "price": total_price
128|    }
129|
130|def calculate_policy_end_date(start_date: str, duration: str) -> str:
131|    """Calculate policy end date based on start date and duration"""
132|    start = datetime.fromisoformat(start_date)
133|    
134|    duration_days = {
135|        "1-day": 1,
136|        "3-days": 3,
137|        "1-week": 7,
138|        "2-weeks": 14,
139|        "1-month": 30
140|    }
141|    
142|    days = duration_days.get(duration, 1)
143|    end_date = start + timedelta(days=days)
144|    
145|    return end_date.strftime('%Y-%m-%d')
146|
147|def generate_policy_number() -> str:
148|    """Generate a unique policy number"""
149|    prefix = "SI"  # SwiftInsure
150|    timestamp = datetime.now().strftime("%Y%m%d")
151|    random_suffix = f"{random.randint(1000, 9999)}"
152|    return f"{prefix}-{timestamp}-{random_suffix}"
153|
154|# API Routes
155|@api_router.get("/")
156|async def root():
157|    return {"message": "SwiftInsure API - Car Insurance Platform"}
158|
159|@api_router.post("/quote", response_model=Quote)
160|async def create_quote(quote_request: QuoteRequest):
161|    """Generate a car insurance quote"""
162|    try:
163|        # Calculate quote pricing
164|        pricing = calculate_quote_price(quote_request)
165|        
166|        # Create quote object
167|        quote = Quote(
168|            price=pricing["price"],
169|            basePremium=pricing["basePremium"],
170|            tax=pricing["tax"],
171|            validUntil=(datetime.now(timezone.utc) + timedelta(hours=24)).isoformat()
172|        )
173|        
174|        # Store quote in database
175|        quote_dict = quote.dict()
176|        await db.quotes.insert_one(quote_dict)
177|        
178|        logging.info(f"Quote generated: {quote.id} for {quote_request.email}")
179|        
180|        return quote
181|        
182|    except Exception as e:
183|        logging.error(f"Error generating quote: {str(e)}")
184|        raise HTTPException(status_code=500, detail="Failed to generate quote")
185|
186|@api_router.post("/purchase", response_model=Policy)
187|async def purchase_policy(purchase_request: PurchaseRequest):
188|    """Purchase an insurance policy"""
189|    try:
190|        # Get the quote from database
191|        quote_data = await db.quotes.find_one({"id": purchase_request.quoteId})
192|        
193|        if not quote_data:
194|            raise HTTPException(status_code=404, detail="Quote not found")
195|        
196|        # Check if quote is still valid
197|        valid_until = datetime.fromisoformat(quote_data["validUntil"].replace('Z', '+00:00'))
198|        if datetime.now(timezone.utc) > valid_until:
199|            raise HTTPException(status_code=400, detail="Quote has expired")
200|        
201|        # Calculate policy dates
202|        start_date = purchase_request.formData.startDate
203|        end_date = calculate_policy_end_date(start_date, purchase_request.formData.duration)
204|        
205|        # Create policy
206|        policy = Policy(
207|            policyNumber=generate_policy_number(),
208|            startDate=start_date,
209|            endDate=end_date,
210|            premium=quote_data["price"]
211|        )
212|        
213|        # Store policy in database
214|        policy_dict = policy.dict()
215|        policy_dict["formData"] = purchase_request.formData.dict()
216|        policy_dict["quoteId"] = purchase_request.quoteId
217|        
218|        await db.policies.insert_one(policy_dict)
219|        
220|        logging.info(f"Policy purchased: {policy.policyNumber} for {purchase_request.formData.email}")
221|        
222|        return policy
223|        
224|    except HTTPException:
225|        raise
226|    except Exception as e:
227|        logging.error(f"Error purchasing policy: {str(e)}")
228|        raise HTTPException(status_code=500, detail="Failed to purchase policy")
229|
230|@api_router.get("/policies", response_model=List[dict])
231|async def get_policies(email: Optional[str] = None):
232|    """Get policies (optionally filtered by email)"""
233|    try:
234|        query = {}
235|        if email:
236|            query["formData.email"] = email
237|        
238|        policies = await db.policies.find(query).to_list(length=100)
239|        
240|        # Convert ObjectId to string and clean up the response
241|        for policy in policies:
242|            if "_id" in policy:
243|                del policy["_id"]
244|            policy["created_at"] = policy["created_at"].isoformat() if "created_at" in policy else None
245|        
246|        return policies
247|        
248|    except Exception as e:
249|        logging.error(f"Error retrieving policies: {str(e)}")
250|        raise HTTPException(status_code=500, detail="Failed to retrieve policies")
251|
252|@api_router.get("/policy/{policy_number}")
253|async def get_policy(policy_number: str):
254|    """Get a specific policy by policy number"""
255|    try:
256|        policy = await db.policies.find_one({"policyNumber": policy_number})
257|        
258|        if not policy:
259|            raise HTTPException(status_code=404, detail="Policy not found")
260|        
261|        # Clean up the response
262|        if "_id" in policy:
263|            del policy["_id"]
264|        policy["created_at"] = policy["created_at"].isoformat() if "created_at" in policy else None
265|        
266|        return policy
267|        
268|    except HTTPException:
269|        raise
270|    except Exception as e:
271|        logging.error(f"Error retrieving policy: {str(e)}")
272|        raise HTTPException(status_code=500, detail="Failed to retrieve policy")
273|
274|@api_router.get("/quotes", response_model=List[dict])
275|async def get_quotes():
276|    """Get all quotes (for admin purposes)"""
277|    try:
278|        quotes = await db.quotes.find().to_list(length=100)
279|        
280|        # Clean up the response
281|        for quote in quotes:
282|            if "_id" in quote:
283|                del quote["_id"]
284|            quote["created_at"] = quote["created_at"].isoformat() if "created_at" in quote else None
285|        
286|        return quotes
287|        
288|    except Exception as e:
289|        logging.error(f"Error retrieving quotes: {str(e)}")
290|        raise HTTPException(status_code=500, detail="Failed to retrieve quotes")
291|
292|# Health check endpoint
293|@api_router.get("/health")
294|async def health_check():
295|    """Health check endpoint"""
296|    try:
297|        # Test database connection
298|        await db.command("ping")
299|        return {
300|            "status": "healthy",
301|            "timestamp": datetime.now(timezone.utc).isoformat(),
302|            "database": "connected"
303|        }
304|    except Exception as e:
305|        logging.error(f"Health check failed: {str(e)}")
306|        raise HTTPException(status_code=503, detail="Service unavailable")
307|
308|# Include the router in the main app
309|app.include_router(api_router)
310|
311|app.add_middleware(
312|    CORSMiddleware,
313|    allow_credentials=True,
314|    allow_origins=os.environ.get('CORS_ORIGINS', '*').split(','),
315|    allow_methods=["*"],
316|    allow_headers=["*"],
317|)
318|
319|# Configure logging
320|logging.basicConfig(
321|    level=logging.INFO,
322|    format='%(asctime)s - %(name)s - %(levelname)s - %(message)s'
323|)
324|logger = logging.getLogger(__name__)
325|
326|@app.on_event("startup")
327|async def startup_event():
328|    logger.info("SwiftInsure API started successfully")
329|
330|@app.on_event("shutdown")
331|async def shutdown_db_client():
332|    client.close()
333|    logger.info("Database connection closed")


/app/frontend/src/index.js:
1|import React from "react";
2|import ReactDOM from "react-dom/client";
3|import "./index.css";
4|import App from "./App";
5|
6|// Suppress ResizeObserver error in development
7|if (process.env.NODE_ENV === 'development') {
8|  const resizeObserverErr = window.ResizeObserver;
9|  window.ResizeObserver = class ResizeObserver extends resizeObserverErr {
10|    constructor(callback) {
11|      super((entries, observer) => {
12|        try {
13|          callback(entries, observer);
14|        } catch (e) {
15|          // Swallow the ResizeObserver loop limit exceeded errors
16|          if (e.message.includes('ResizeObserver loop completed with undelivered notifications')) {
17|            // Ignore this specific error
18|            return;
19|          }
20|          throw e;
21|        }
22|      });
23|    }
24|  };
25|}
26|
27|const root = ReactDOM.createRoot(document.getElementById("root"));
28|root.render(
29|  <React.StrictMode>
30|    <App />
31|  </React.StrictMode>,
32|);
33|


