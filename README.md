import discord 
import random 
from discord.ext import commands

intents = discord.Intents.default()
intents.message_content = True
bot = commands.Bot(command_prefix='$', intents=intents)

datos = ["¿sabias que, ? Cada año, casi 4 millones de personas mueren prematuramente por la contaminación del aire en interiores, ¿quieres evitar esto? entonces te damos un tip, ahorra agua cuando te cepillas, (no dejes abierta la llave/grifo mientras te cepillas) para evitar consumir mucha energia y agua, ya que el agua ayuda a limpiar el aire. ","Sabias que: El suelo al degradarse pierde sus propiedades físico-químicas y como consecuencia este deja de ser productivo para servicios como la agricultura o los servicios ecosistémicos. Las causas de la degradación del suelo se deben a diferentes factores: la tala intensiva, la agricultura extensiva, el sobrepastoreo, los incendios forestales, las construcciones o la sobreexplotación de recursos hídricos.   Una solución para evitar o minimizar este problema, sería la implantación de políticas medioambientales que regulen el uso del suelo","Sabías que según la Organización Mundial de la Salud, la contaminación del aire es responsable de aproximadamente 7 millones de muertes cada año en todo el mundo. La exposición a partículas finas en el aire puede penetrar profundamente en los pulmones y el sistema cardiovascular, causando enfermedades respiratorias y cardíacas. Cómo evitarlo? Para evitar la contaminación del aire puedes optar por el transporte público, caminar, andar en bicicleta o utilizar vehículos eléctricos en lugar de vehículos de combustión interna."]

@bot.event
async def on_ready():
    print(f'We have logged in as {bot.user}')
    
@bot.command (description='For when you wanna settle the score some other way')
async def dato(ctx, *choices: str):
    """Chooses between multiple choices."""
    await ctx.send(random.choice(datos))

bot.run("")
