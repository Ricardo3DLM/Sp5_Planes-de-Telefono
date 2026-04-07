Info. Proyecto de Sprint 5: "¿Cuál es la mejor tarifa?"

Análisis de datos y data wrangling.

La base de datos contiene información sobre paquetes de telecomunicaciones (Surf y Ultimate) y sus clientes.
Tablas de Datos (5):

La tabla users (datos sobre los usuarios):
	user_id: identificador único del usuario.
	first_name: nombre del usuario.
	last_name: apellido del usuario.
	age: edad del usuario (en años).
	reg_date: fecha de suscripción (dd, mm, aa).
	churn_date: la fecha en la que el usuario dejó de usar el servicio (si el valor es ausente, la tarifa 
	se estaba usando cuando fue extraída esta base de datos).
	city: ciudad de residencia del usuario.
	plan: nombre de la tarifa.

La tabla calls (datos sobre las llamadas):
	id: identificador único de la llamada.
	call_date: fecha de la llamada.
	duration: duración de la llamada (en minutos).
	user_id: el identificador del usuario que realiza la llamada.

La tabla messages (datos sobre los SMS):
	id: identificador único del SMS.
	message_date: fecha del SMS.
	user_id: el identificador del usuario que manda el SMS.

La tabla internet (datos sobre las sesiones web):
	id: identificador único de la sesión.
	mb_used: el volumen de datos gastados durante la sesión (en megabytes).
	session_date: fecha de la sesión web.
	user_id: identificador del usuario.

La tabla plans (datos sobre las tarifas):
	plan_name: nombre de la tarifa.
	usd_monthly_fee: pago mensual en dólares estadounidenses.
	minutes_included: minutos incluidos al mes.
	messages_included: SMS incluidos al mes.
	mb_per_month_included: datos incluidos al mes (en megabytes).
	usd_per_minute: precio por minuto tras exceder los límites del paquete (por ejemplo, si el paquete incluye 
	100 minutos, el operador cobrará el minuto 101).
	usd_per_message: precio por SMS tras exceder los límites del paquete.
	usd_per_gb: precio por gigabyte de los datos extra tras exceder los límites del paquete (1 GB = 1024 
	megabytes).


Conclusiones:

Después de la limpieza de datos, creación de tablas (histogramas, boxplots, barras, líneas), y una prueba de hipótesis
para identificar diferencias en ingresos por regiones y planes, se concluye que:

- Los usuarios de ambos planes consumen más llamadas, mensajes, y MB conforme avanza el año. Esto se concluye sin 
ignorar que el número de usuarios incrementó durante el año, ya que esto no influyó en el uso por usuario, 
solamente en el uso total.
- El plan Surf genera más ingresos en promedio que el Ultimate si se evalua el año completo. Mes a mes, el plan 
Ultimate genera más ingresos hasta el mes de Agosto, y el de Surf a partir de Septiembre genera más en total, pero 
debe de mencionarse que el plan Surf tiene más usuarios que el plan Ultimate.
- En general, los del plan Ultimate no se exceden de sus límites salvo por los MB al final del año, mientras que 
los de Surf sí se exceden en llamadas, mensajes, y datos de internet.
Para la empresa, lo ideal sería que todos los usuarios tengan el plan Ultimate por 8 meses y que luego todos 
cambiaran al plan Surf para maximizar los ingresos. Para los usuarios, lo ideal sería la inversa para pagar lo menos 
posible.
- Los mensajes son el beneficio menos utilizado por los usuarios, y los usuarios que se exceden de Surf lo hacen por 
muy poco.
- Según las pruebas de hipótesis, en general los usuarios de Surf generan menos ingresos que los de Ultimate (indicado 
por el t-stat negativo), y de igual manera los usuarios de NY-NJ generan menos ingresos que el resto de las ciudades de 
la muestra.
