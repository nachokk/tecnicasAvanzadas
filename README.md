<p><div class="toc">
<ul>
<li><a href="#getting-started">Getting started</a><ul>
<li><a href="#status">Status</a><ul>
<li><ul>
<li><a href="#example">Example</a></li>
</ul>
</li>
</ul>
</li>
<li><a href="#jobs">Jobs</a><ul>
<li><ul>
<li><a href="#example-1">Example</a></li>
</ul>
</li>
</ul>
</li>
<li><a href="#metrics">Metrics</a><ul>
<li><ul>
<li><a href="#example-2">Example</a></li>
</ul>
</li>
</ul>
</li>
</ul>
</li>
</ul>
</div>
</p>



<h1 id="getting-started">Getting started</h1>

<p>Olympus is a monitor system for P13n apps. It has a rest-api where you can see spec (alpha version) from <a href="http://backoffice.despegar.com/olympus/docs">http://backoffice.despegar.com/olympus/docs</a></p>



<h2 id="status">Status</h2>

<p>A status is a set of alarms that an application instance notify to olympus.</p>



<h4 id="example">Example</h4>



<pre class="prettyprint"><code class=" hljs json">  {
    "<span class="hljs-attribute">app_details</span>": <span class="hljs-value">{
      "<span class="hljs-attribute">app_name</span>": <span class="hljs-value"><span class="hljs-string">"euler"</span></span>,
      "<span class="hljs-attribute">env</span>": <span class="hljs-value"><span class="hljs-string">"prod"</span></span>,
      "<span class="hljs-attribute">host_name</span>": <span class="hljs-value"><span class="hljs-string">"euler-web-00"</span>
    </span>}</span>,
    "<span class="hljs-attribute">data</span>": <span class="hljs-value">{
      "<span class="hljs-attribute">general</span>": <span class="hljs-value"><span class="hljs-string">"RED"</span></span>,
      "<span class="hljs-attribute">properties</span>": <span class="hljs-value">{
          "<span class="hljs-attribute">alarm_name</span>" : <span class="hljs-value"><span class="hljs-string">"RED"</span></span>,
          "<span class="hljs-attribute">alarm_name2</span>" : <span class="hljs-value"><span class="hljs-string">"GREEN"</span></span>,
          "<span class="hljs-attribute">alarm_name3</span>" : <span class="hljs-value"><span class="hljs-string">"YELLOW"</span>
      </span>}
    </span>}
  </span>}
</code></pre>

<p>The <code>properties</code> object has the alarms that an application notify, possible values of that properties are [RED, YELLOW,GREEN] like a semaphore. <code>general</code> is an optional field , refers to app general status based on the other alarms</p>

<h2 id="jobs">Jobs</h2>

<p>You can also notify a job execution.  First you have to submit the gracetime that you want a job to run, later when the job runs you have to notify olympus that the job run.</p>



<h4 id="example-1">Example</h4>



<div class="sequence-diagram"><svg height="441" version="1.1" width="449.46875" xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink" style="overflow: hidden; position: relative; top: -0.375px;"><desc style="-webkit-tap-highlight-color: rgba(0, 0, 0, 0);">Created with Raphaël 2.1.2</desc><defs style="-webkit-tap-highlight-color: rgba(0, 0, 0, 0);"><path stroke-linecap="round" d="M5,0 0,2.5 5,5z" id="raphael-marker-block" style="-webkit-tap-highlight-color: rgba(0, 0, 0, 0);"></path><marker id="raphael-marker-endblock55-obj3381" markerHeight="5" markerWidth="5" orient="auto" refX="2.5" refY="2.5" style="-webkit-tap-highlight-color: rgba(0, 0, 0, 0);"><use xmlns:xlink="http://www.w3.org/1999/xlink" xlink:href="#raphael-marker-block" transform="rotate(180 2.5 2.5) scale(1,1)" stroke-width="1.0000" fill="#000" stroke="none" style="-webkit-tap-highlight-color: rgba(0, 0, 0, 0);"></use></marker><marker id="raphael-marker-endblock55-obj3389" markerHeight="5" markerWidth="5" orient="auto" refX="2.5" refY="2.5" style="-webkit-tap-highlight-color: rgba(0, 0, 0, 0);"><use xmlns:xlink="http://www.w3.org/1999/xlink" xlink:href="#raphael-marker-block" transform="rotate(180 2.5 2.5) scale(1,1)" stroke-width="1.0000" fill="#000" stroke="none" style="-webkit-tap-highlight-color: rgba(0, 0, 0, 0);"></use></marker><marker id="raphael-marker-endblock55-obj3395" markerHeight="5" markerWidth="5" orient="auto" refX="2.5" refY="2.5" style="-webkit-tap-highlight-color: rgba(0, 0, 0, 0);"><use xmlns:xlink="http://www.w3.org/1999/xlink" xlink:href="#raphael-marker-block" transform="rotate(180 2.5 2.5) scale(1,1)" stroke-width="1.0000" fill="#000" stroke="none" style="-webkit-tap-highlight-color: rgba(0, 0, 0, 0);"></use></marker><marker id="raphael-marker-endblock55-obj3400" markerHeight="5" markerWidth="5" orient="auto" refX="2.5" refY="2.5" style="-webkit-tap-highlight-color: rgba(0, 0, 0, 0);"><use xmlns:xlink="http://www.w3.org/1999/xlink" xlink:href="#raphael-marker-block" transform="rotate(180 2.5 2.5) scale(1,1)" stroke-width="1.0000" fill="#000" stroke="none" style="-webkit-tap-highlight-color: rgba(0, 0, 0, 0);"></use></marker></defs><rect x="10" y="20" width="52.5625" height="39" rx="0" ry="0" fill="none" stroke="#000000" stroke-width="2" style="-webkit-tap-highlight-color: rgba(0, 0, 0, 0);"></rect><rect x="20" y="30" width="32.5625" height="19" rx="0" ry="0" fill="#ffffff" stroke="none" style="-webkit-tap-highlight-color: rgba(0, 0, 0, 0);"></rect><text x="36.28125" y="39.5" text-anchor="middle" font-family="Andale Mono, monospace" font-size="16px" stroke="none" fill="#000000" style="-webkit-tap-highlight-color: rgba(0, 0, 0, 0); text-anchor: middle; font-family: 'Andale Mono', monospace; font-size: 16px;"><tspan dy="5.5" style="-webkit-tap-highlight-color: rgba(0, 0, 0, 0);">Euler</tspan></text><rect x="10" y="382" width="52.5625" height="39" rx="0" ry="0" fill="none" stroke="#000000" stroke-width="2" style="-webkit-tap-highlight-color: rgba(0, 0, 0, 0);"></rect><rect x="20" y="392" width="32.5625" height="19" rx="0" ry="0" fill="#ffffff" stroke="none" style="-webkit-tap-highlight-color: rgba(0, 0, 0, 0);"></rect><text x="36.28125" y="401.5" text-anchor="middle" font-family="Andale Mono, monospace" font-size="16px" stroke="none" fill="#000000" style="-webkit-tap-highlight-color: rgba(0, 0, 0, 0); text-anchor: middle; font-family: 'Andale Mono', monospace; font-size: 16px;"><tspan dy="5.5" style="-webkit-tap-highlight-color: rgba(0, 0, 0, 0);">Euler</tspan></text><path fill="none" stroke="#000000" d="M36.28125,59L36.28125,382" stroke-width="2" style="-webkit-tap-highlight-color: rgba(0, 0, 0, 0);"></path><rect x="157.375" y="20" width="76" height="39" rx="0" ry="0" fill="none" stroke="#000000" stroke-width="2" style="-webkit-tap-highlight-color: rgba(0, 0, 0, 0);"></rect><rect x="167.375" y="30" width="56" height="19" rx="0" ry="0" fill="#ffffff" stroke="none" style="-webkit-tap-highlight-color: rgba(0, 0, 0, 0);"></rect><text x="195.375" y="39.5" text-anchor="middle" font-family="Andale Mono, monospace" font-size="16px" stroke="none" fill="#000000" style="-webkit-tap-highlight-color: rgba(0, 0, 0, 0); text-anchor: middle; font-family: 'Andale Mono', monospace; font-size: 16px;"><tspan dy="5.5" style="-webkit-tap-highlight-color: rgba(0, 0, 0, 0);">Olympus</tspan></text><rect x="157.375" y="382" width="76" height="39" rx="0" ry="0" fill="none" stroke="#000000" stroke-width="2" style="-webkit-tap-highlight-color: rgba(0, 0, 0, 0);"></rect><rect x="167.375" y="392" width="56" height="19" rx="0" ry="0" fill="#ffffff" stroke="none" style="-webkit-tap-highlight-color: rgba(0, 0, 0, 0);"></rect><text x="195.375" y="401.5" text-anchor="middle" font-family="Andale Mono, monospace" font-size="16px" stroke="none" fill="#000000" style="-webkit-tap-highlight-color: rgba(0, 0, 0, 0); text-anchor: middle; font-family: 'Andale Mono', monospace; font-size: 16px;"><tspan dy="5.5" style="-webkit-tap-highlight-color: rgba(0, 0, 0, 0);">Olympus</tspan></text><path fill="none" stroke="#000000" d="M195.375,59L195.375,382" stroke-width="2" style="-webkit-tap-highlight-color: rgba(0, 0, 0, 0);"></path><rect x="46.28125" y="74.5" width="139.09375" height="19" rx="0" ry="0" fill="#ffffff" stroke="none" style="-webkit-tap-highlight-color: rgba(0, 0, 0, 0);"></rect><text x="115.828125" y="84" text-anchor="middle" font-family="Andale Mono, monospace" font-size="16px" stroke="none" fill="#000000" style="-webkit-tap-highlight-color: rgba(0, 0, 0, 0); text-anchor: middle; font-family: 'Andale Mono', monospace; font-size: 16px;"><tspan dy="5.5" style="-webkit-tap-highlight-color: rgba(0, 0, 0, 0);">gracetime(ranking,30)</tspan></text><path fill="none" stroke="#000000" d="M36.28125,98C36.28125,98,163.37748353742063,98,190.37302142256613,98" stroke-width="2" marker-end="url(#raphael-marker-endblock55-obj3381)" stroke-dasharray="0" style="-webkit-tap-highlight-color: rgba(0, 0, 0, 0);"></path><rect x="215.375" y="118" width="106.53125" height="29" rx="0" ry="0" fill="none" stroke="#000000" stroke-width="2" style="-webkit-tap-highlight-color: rgba(0, 0, 0, 0);"></rect><rect x="220.375" y="123" width="96.53125" height="19" rx="0" ry="0" fill="#ffffff" stroke="none" style="-webkit-tap-highlight-color: rgba(0, 0, 0, 0);"></rect><text x="268.640625" y="132.5" text-anchor="middle" font-family="Andale Mono, monospace" font-size="16px" stroke="none" fill="#000000" style="-webkit-tap-highlight-color: rgba(0, 0, 0, 0); text-anchor: middle; font-family: 'Andale Mono', monospace; font-size: 16px;"><tspan dy="5.5" style="-webkit-tap-highlight-color: rgba(0, 0, 0, 0);">Save gracetime</tspan></text><rect x="220.375" y="167" width="124.59375" height="19" rx="0" ry="0" fill="#ffffff" stroke="none" style="-webkit-tap-highlight-color: rgba(0, 0, 0, 0);"></rect><text x="282.671875" y="176.5" text-anchor="middle" font-family="Andale Mono, monospace" font-size="16px" stroke="none" fill="#000000" style="-webkit-tap-highlight-color: rgba(0, 0, 0, 0); text-anchor: middle; font-family: 'Andale Mono', monospace; font-size: 16px;"><tspan dy="5.5" style="-webkit-tap-highlight-color: rgba(0, 0, 0, 0);">check job execution</tspan></text><path fill="none" stroke="#000000" d="M195.375,162L215.375,162" stroke-width="2" stroke-dasharray="6,2" style="-webkit-tap-highlight-color: rgba(0, 0, 0, 0);"></path><path fill="none" stroke="#000000" d="M215.375,162L215.375,196" stroke-width="2" stroke-dasharray="6,2" style="-webkit-tap-highlight-color: rgba(0, 0, 0, 0);"></path><path fill="none" stroke="#000000" d="M215.375,196C215.375,196,206.2941131591797,196,200.3702533841133,196" stroke-width="2" stroke-dasharray="6,2" marker-end="url(#raphael-marker-endblock55-obj3389)" style="-webkit-tap-highlight-color: rgba(0, 0, 0, 0);"></path><rect x="215.375" y="206" width="128.4375" height="29" rx="0" ry="0" fill="none" stroke="#000000" stroke-width="2" style="-webkit-tap-highlight-color: rgba(0, 0, 0, 0);"></rect><rect x="220.375" y="211" width="118.4375" height="19" rx="0" ry="0" fill="#ffffff" stroke="none" style="-webkit-tap-highlight-color: rgba(0, 0, 0, 0);"></rect><text x="279.59375" y="220.5" text-anchor="middle" font-family="Andale Mono, monospace" font-size="16px" stroke="none" fill="#000000" style="-webkit-tap-highlight-color: rgba(0, 0, 0, 0); text-anchor: middle; font-family: 'Andale Mono', monospace; font-size: 16px;"><tspan dy="5.5" style="-webkit-tap-highlight-color: rgba(0, 0, 0, 0);">ranking status RED</tspan></text><rect x="57.21875" y="250.5" width="117.21875" height="19" rx="0" ry="0" fill="#ffffff" stroke="none" style="-webkit-tap-highlight-color: rgba(0, 0, 0, 0);"></rect><text x="115.828125" y="260" text-anchor="middle" font-family="Andale Mono, monospace" font-size="16px" stroke="none" fill="#000000" style="-webkit-tap-highlight-color: rgba(0, 0, 0, 0); text-anchor: middle; font-family: 'Andale Mono', monospace; font-size: 16px;"><tspan dy="5.5" style="-webkit-tap-highlight-color: rgba(0, 0, 0, 0);">notifyJob(ranking)</tspan></text><path fill="none" stroke="#000000" d="M36.28125,274C36.28125,274,163.37748353742063,274,190.37302142256613,274" stroke-width="2" marker-end="url(#raphael-marker-endblock55-obj3395)" stroke-dasharray="6,2" style="-webkit-tap-highlight-color: rgba(0, 0, 0, 0);"></path><rect x="220.375" y="294" width="124.59375" height="19" rx="0" ry="0" fill="#ffffff" stroke="none" style="-webkit-tap-highlight-color: rgba(0, 0, 0, 0);"></rect><text x="282.671875" y="303.5" text-anchor="middle" font-family="Andale Mono, monospace" font-size="16px" stroke="none" fill="#000000" style="-webkit-tap-highlight-color: rgba(0, 0, 0, 0); text-anchor: middle; font-family: 'Andale Mono', monospace; font-size: 16px;"><tspan dy="5.5" style="-webkit-tap-highlight-color: rgba(0, 0, 0, 0);">check job execution</tspan></text><path fill="none" stroke="#000000" d="M195.375,289L215.375,289" stroke-width="2" stroke-dasharray="6,2" style="-webkit-tap-highlight-color: rgba(0, 0, 0, 0);"></path><path fill="none" stroke="#000000" d="M215.375,289L215.375,323" stroke-width="2" stroke-dasharray="6,2" style="-webkit-tap-highlight-color: rgba(0, 0, 0, 0);"></path><path fill="none" stroke="#000000" d="M215.375,323C215.375,323,206.2941131591797,323,200.3702533841133,323" stroke-width="2" stroke-dasharray="6,2" marker-end="url(#raphael-marker-endblock55-obj3400)" style="-webkit-tap-highlight-color: rgba(0, 0, 0, 0);"></path><rect x="215.375" y="333" width="146.09375" height="29" rx="0" ry="0" fill="none" stroke="#000000" stroke-width="2" style="-webkit-tap-highlight-color: rgba(0, 0, 0, 0);"></rect><rect x="220.375" y="338" width="136.09375" height="19" rx="0" ry="0" fill="#ffffff" stroke="none" style="-webkit-tap-highlight-color: rgba(0, 0, 0, 0);"></rect><text x="288.421875" y="347.5" text-anchor="middle" font-family="Andale Mono, monospace" font-size="16px" stroke="none" fill="#000000" style="-webkit-tap-highlight-color: rgba(0, 0, 0, 0); text-anchor: middle; font-family: 'Andale Mono', monospace; font-size: 16px;"><tspan dy="5.5" style="-webkit-tap-highlight-color: rgba(0, 0, 0, 0);">ranking status GREEN</tspan></text></svg></div>



<h2 id="metrics">Metrics</h2>

<p>You can submit metrics to olympus </p>



<h4 id="example-2">Example</h4>



<pre class="prettyprint"><code class=" hljs json">{
  "<span class="hljs-attribute">app_details</span>": <span class="hljs-value">{
    "<span class="hljs-attribute">app_name</span>": <span class="hljs-value"><span class="hljs-string">"euler"</span></span>,
    "<span class="hljs-attribute">env</span>": <span class="hljs-value"><span class="hljs-string">"prod"</span></span>,
    "<span class="hljs-attribute">host_name</span>": <span class="hljs-value"><span class="hljs-string">"euler-web-00"</span>
  </span>}</span>,
  "<span class="hljs-attribute">data</span>": <span class="hljs-value">[
    {
      "<span class="hljs-attribute">name</span>": <span class="hljs-value"><span class="hljs-string">"rejected_events"</span></span>,
      "<span class="hljs-attribute">value</span>": <span class="hljs-value"><span class="hljs-number">100</span>
    </span>},
    {
      "<span class="hljs-attribute">name</span>": <span class="hljs-value"><span class="hljs-string">"received_events"</span></span>,
      "<span class="hljs-attribute">value</span>": <span class="hljs-value"><span class="hljs-number">500</span>
    </span>}
  ]
</span>}</code></pre>

<blockquote>
  <p><strong>Note:</strong></p>
  
  <ul>
  <li>Check java api <a href="https://github.com/despegar/olympus">https://github.com/despegar/olympus</a></li>
  </ul>
</blockquote>