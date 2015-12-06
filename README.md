# route-a11y

<h2>Overview</h2>
<p>
  This is my attempt to add accessibility to angular SPA application. Router UI is used to navigate between
  different application states. Therefore, the navigation and footer stays the same and only the main area gets
  updated.
</p>

When a user clicks on a navigation link that changes the state the goal is:
<ul>
  <li>To push the dynamic content to screen reader to be announced</li>
  <li>Move focus should to the new dynamic content</li>
</ul>

<h2>Push dynamic content</h2>

I tried to use <b>aria-live</b> but somehow it did not work for this case. Role <b>alert</b> made the magic:

<img class="img-responsive" src="src/assets/images/rolealert.png" alt="code with role alert">

<h2>Focus management</h2>

<b>AutoFocus</b> directive was added to dynamically move the focus when on the success routing event.

<h2>How to test</h2>
I tested the solution using Voice Over on Mac, NVDA on Windows and ChromVox plugin. Here is screen log from
Voice Over when I clicked on 'Route2' navigation link. As you see the screen reader was able to announce the new
dynamic content automatically.

<img class="img-responsive" src="src/assets/images/voiceover.png" alt="voice over screen capture">

<h2>Suggestions</h2>
Please let me know if you solved this problem using any other means.


