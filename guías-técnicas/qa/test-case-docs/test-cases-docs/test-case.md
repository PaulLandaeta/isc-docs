<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 49%" />
</colgroup>
<thead>
<tr class="header">
<th colspan="2"><strong>Test Case Specifics</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td colspan="2"><strong>Test Title:</strong> #186 Feat: color de tags
dependiendo de la misma</td>
</tr>
<tr class="even">
<td colspan="2"><strong>Test Description:</strong> “Que los colores sean
correspondientes a cada tipo de manera que se identifique correctamente
el tipo de problema al buscar en la tabla de problemas” Se verifica que
los cambios realizados se hayan aplicado cumpliendo las métricas
establecidas en la tarea.</td>
</tr>
<tr class="odd">
<td><p><strong>Test Accounts/Test Login:</strong></p>
<p><strong>Username:</strong> <a
href="mailto:sudo@gmail.com">sudo@gmail.com</a></p>
<p><strong>Password:</strong> StrongPassword12</p></td>
<td><strong>Note:</strong></td>
</tr>
<tr class="even">
<td colspan="2"><p><strong>Pre-requisite(s):</strong></p>
<ul>
<li><p>Acceso al sistema y a la página de registro.</p></li>
<li><p>Navegador Web</p></li>
<li><p>Ejecutar backend</p></li>
</ul></td>
</tr>
</tbody>
</table>

| **Test Case Procedures** |
|--------------------------|
| **Test Result: FAIL**    |

<table>
<colgroup>
<col style="width: 6%" />
<col style="width: 23%" />
<col style="width: 24%" />
<col style="width: 38%" />
<col style="width: 6%" />
</colgroup>
<thead>
<tr class="header">
<th><em><strong>Step</strong></em></th>
<th><em><strong>Action</strong></em></th>
<th><em><strong>Expected Result</strong></em></th>
<th><em><strong>Actual Results</strong></em></th>
<th><p><em><strong>Pass</strong></em></p>
<p><em><strong>Fail</strong></em></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><ol type="1">
<li></li>
</ol></td>
<td><p>Ingresar a: <a
href="https://upb-forces-qa.vercel.app/#/">https://upb-forces-qa.vercel.app/#/</a></p>
<p>Logearse con los datos datos de la cuenta o la del admin.</p></td>
<td>Se debe poder logearse sin ningún tipo de problema.</td>
<td>Se logea sin ningún tipo de problema.</td>
<td><strong>✓</strong></td>
</tr>
<tr class="even">
<td><ol start="2" type="1">
<li></li>
</ol></td>
<td>Ingresar a la pantalla “Problemas”. Ver la columna Etiquetas.</td>
<td>Los colores de etiqueta de cada tarea deberían ser de acuerdo a la
etiqueta que se haya colocado.</td>
<td>El color de etiqueta es el mismo para cualquier problema, sin
diferenciarse incluso teniendo distintas etiquetas cada uno.</td>
<td></td>
</tr>
<tr class="odd">
<td><ol start="3" type="1">
<li></li>
</ol></td>
<td>Ingresar a la pantalla “Problemas”. Ver la columna Etiquetas</td>
<td>El color de etiqueta debería ser completamente visible para el
usuario indicando el nombre de la etiqueta y su color.</td>
<td>No muestra que tipo de etiqueta es al no mostrar el nombre de la
etiqueta y al mostrar una línea muy poco visible para el usuario.</td>
<td><strong>✓</strong></td>
</tr>
<tr class="even">
<td><ol start="4" type="1">
<li></li>
</ol></td>
<td>Ingresar a la pantalla “Problemas”. Ver la columna Etiquetas</td>
<td>Una tarea que tiene varias etiquetas debería mostrar el distinto
tipo de colores de etiquetas con sus nombres respectivos a las etiquetas
del problema en una sola celda de la tabla.</td>
<td>Se creó una tarea con varias etiquetas, pero solo muestra una
etiqueta que es la misma que de las demás tareas.</td>
<td><strong>✕</strong></td>
</tr>
<tr class="odd">
<td><ol start="5" type="1">
<li></li>
</ol></td>
<td>Cambiar a modo celular y Tablet en el modo resposive, probar los
pasos 1-4 anteriores del mismo modo.</td>
<td><p>La etiqueta del problema debería cumplir las siguientes
características:</p>
<ul>
<li><p>Color según la etiqueta del problema</p></li>
<li><p>Visible para el usuario</p></li>
<li><p>Varias etiquetas en caso de haber creado un problema
así.</p></li>
</ul></td>
<td><p>No cumple con ninguno de las características requeridas:</p>
<ul>
<li><p>El color es el mismo para todos los problemas.</p></li>
<li><p>No es muy visible para el usuario.</p></li>
<li><p>No se distingue de una tarea de muchas etiquetas con una de una
sola.</p></li>
</ul></td>
<td></td>
</tr>
<tr class="even">
<td><ol start="6" type="1">
<li></li>
</ol></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td colspan="5"><strong>Pruebas (Estado Pass Test Case o
Fail)</strong></td>
</tr>
<tr class="even">
<td colspan="5"><strong>Imagenes</strong><img src="media/image1.png"
style="width:0.91118in;height:2.07584in" /> <img src="media/image1.png"
style="width:0.91118in;height:2.07584in" /> <strong>o (VIDEO LINK POR
DRIVE)</strong></td>
</tr>
</tbody>
</table>

| **Tester Information**                  |                                       |
|-----------------------------------------|---------------------------------------|
| **Tester(s) Name(s): Jhonatan Cabezas** | **Test Date(s):06/26/24 -- 10:35 PM** |
| **Windows Version: 11 Home**            | **Internet Browser: Google Chrome**   |
