# kivy-hw
from kivy.app import App
from kivy.uix.button import Button
from kivy.uix.boxlayout import BoxLayout
from kivy.uix.label import Label
from kivy.uix.screenmanager import ScreenManager, Screen


class FirstScr(Screen):
   def __init__(self, name='first'):
      super().__init__(name=name)
      btn = Button(text="Переключиться на другой экран")
      btn.on_press = self.next
      self.add_widget(btn)

   def next(self):
      self.manager.transition.direction = 'left'
      self.manager.current = 'second'

      self.manager.transition.direction = 'right'
      self.manager.current = 'third'

      self.manager.transition.direction = 'up'
      self.manager.current = 'fourth'

      self.manager.transition.direction = 'down'
      self.manager.current = 'fifth'

class SecondScr(Screen):
   def __init__(self, name='second'):
      super().__init__(name=name)
      btn = Button(text="Вернись на первый экран!")
      btn.on_press = self.next
      self.add_widget(btn)

   def next(self):
      self.manager.transition.direction = 'right'
      self.manager.current = 'first'

class ThirdScr(Screen):
   def __init__(self, name='third'):
      super().__init__(name=name)
      btn = Button(text="Вернись на первый экран!")
      btn.on_press = self.next
      self.add_widget(btn)

   def next(self):
      self.manager.transition.direction = 'left'
      self.manager.current = 'first'

class FourthScr(Screen):
   def __init__(self, name='fourth'):
      super().__init__(name=name)
      btn = Button(text="Вернись на первый экран!")
      btn.on_press = self.next
      self.add_widget(btn)

   def next(self):
      self.manager.transition.direction = 'down'
      self.manager.current = 'first'

class FifthScr(Screen):
   def __init__(self, name='fifth'):
      super().__init__(name=name)
      btn = Button(text="Вернись на первый экран!")
      btn.on_press = self.next
      self.add_widget(btn)

   def next(self):
      self.manager.transition.direction = 'up'
      self.manager.current = 'first'

class MyApp(App):
   def build(self):
      sm = ScreenManager()
      sm.add_widget(FirstScr())
      sm.add_widget(SecondScr())
      sm.add_widget(ThirdScr())
      sm.add_widget(FourthScr())
      sm.add_widget(FifthScr())
      return sm


app = MyApp()
app.run()
