this script allows to make a calendar on power bi based on your data, which can be of grat utility when analyzing.
the only thing you need to change is the part between "//", and it is taken freom a column from a facts table that registers operation dates.
You put this in the advanced query (middle-left-top bar) after opening the power query editor when you have already selected the column whe are treating

let<br>
<pre>
	fechas= Table.Column("Venta", //"Fecha"//),<br>
	fecha_min=List.Min('Fechas'),<br>
	fecha_max=List.Max('Fechas'),<br>
	dias=Number.From(Fecha_max - fecha_min) +1,<br>
	Fechas_completas=List-Dates(fecha_min, dias,#duration(1,0,0,0))<br>
</pre>
in <br>
<pre>
	dias<br>
</pre>
	
