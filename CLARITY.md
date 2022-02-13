# Clarity
Clarity is the name of a challenge I personally give myself in plugin development - it aims at eliminating *all* stacktraces, crashes and vague errors with no clear solution to the end-user. It does not eliminate the need for support or questions, but it ensures that anyone who's made a mistake configuring the plugin knows what went wrong and will be able to fix it themselves. It additionally documents as much of the plugin as possible internally to reduce the need for external sources as well as documenting originally unanticipated behaviour that directly impacts the functionality of other plugins.

### Why is it important?
I will admit I'm guilty of this myself, but sometimes mistakes there are strange errors in plugins that crash the plugin altogether and don't make sense - firstly, who the hell is NullPointerException and why has he killed my plugin? You contact the plugin developer and they say you messed up your configuration beyond recognition. Okay, cool, that's fixable, but why does the plugin just outright crash? /reload is as satanic as it is, why do you have to go through all the effort of shutting down the server again, waiting another minute for the server to start (if you're on Spigot) and keep trying to fix the configuration just for it to keep crashing the plugin, no matter what you try?

On the other hand, there's another plugin that stops and tells you there's a syntax error in your configuration. Where? Ah, line 64. You correct it, use the plugin's internal reload command for reloading the config. Takes a few seconds, tells you there's another syntax error elsewhere. Whoops. Correct that, oh crap, you've put "stupid_item" as a material name. Plugin doesn't like that. Okay, let's just correct it. At least it doesn't throw a- uhh. What was it again? 

You get the idea.

### How to I adopt this challenge into my plugin?
You don't need my permission at all; just do it.

Here's what is covered in mentioned challenge:
- Stacktraces. The average server owner/administrator cannot read them. Get rid of them. They're ugly AF. 
  - If a user uses your plugin on the wrong version, let them know.
  - If you disable the plugin and Bukkit screams at you over it, I'm so sorry for your loss. Been there, done that.
- Vague error messages. Be specific.
- Unexpected inputs - make sure your plugin prepares for the possibility of incomplete configuration, strings instead of numbers, mismatched argument length.
