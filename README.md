from manim import *

class aaa(Scene):
  
    def construct(self):
        txt1 = Title('Somas de Riemann')
        
        txt2 = Tex('1. Calcule a área entre o gráfico de f(x) e o eixo x no intervalo de -1 e 3.').scale(0.5).next_to(txt1,DOWN)
        
        txt3 = MathTex("f(x) = {x}^{2} - {4}{x} + {5}").scale(0.5).next_to(txt2,DOWN)

        ax = Axes(
            x_range=[-2, 6, 1],
            y_range=[-2, 6, 1],
            tips=False,
            axis_config={"include_numbers": True}
        ).scale(0.7).next_to(txt1, DOWN, buff=1.8)
        
        graph1 = ax.plot(lambda x: (x-2) ** 2 + 1, x_range=[-0.24, 4.24], use_smoothing=False)

        area = ax.get_area(
            graph1,
            x_range=(0, 3),
            color=(YELLOW_A, MAROON_A, BLUE_A, GREEN_A),
            opacity=1,
        )

        rects = VGroup()

        rects_right1 = ax.get_riemann_rectangles(
            graph1,
            x_range=[0, 3],
            dx=1,
            color=(YELLOW_A, MAROON_A, BLUE_A, GREEN_A),
            input_sample_type="right",
        )
        rects_right2 = ax.get_riemann_rectangles(
            graph1,
            x_range=[0, 3],
            dx=0.5,
            color=(YELLOW_A, MAROON_A, BLUE_A, GREEN_A),
            input_sample_type="right",
        )
        rects_right3 = ax.get_riemann_rectangles(
            graph1,
            x_range=[0, 3],
            dx=0.25,
            color=(YELLOW_A, MAROON_A, BLUE_A, GREEN_A),
            input_sample_type="right",
        )
        rects_right4 = ax.get_riemann_rectangles(
            graph1,
            x_range=[0, 3],
            dx=0.125,
            color=(YELLOW_A, MAROON_A, BLUE_A, GREEN_A),
            input_sample_type="right",
        )
        rects_right5 = ax.get_riemann_rectangles(
            graph1,
            x_range=[0, 3],
            dx=0.0625,
            color=(YELLOW_A, MAROON_A, BLUE_A, GREEN_A),
            input_sample_type="right",
        )
        rects_right6 = ax.get_riemann_rectangles(
            graph1,
            x_range=[0, 3],
            dx=0.03125,
            color=(YELLOW_A, MAROON_A, BLUE_A, GREEN_A),
            input_sample_type="right",
        )
        

        self.play(FadeIn(txt1))
        self.wait(0.5)        
        self.play(Create(txt2))                
        self.play(Create(txt3))                  
        self.play(Create(ax))
        self.wait()
        self.play(Create(graph1))
        self.wait(2)
        self.play(FadeIn(area))
        self.wait(2)
        self.play(FadeOut(area))
        self.play(Create(rects_right1))
        self.wait(4)
        self.play(FadeOut(rects_right1))
        self.play(Create(rects_right2))
        self.wait(4)
        self.play(FadeOut(rects_right2))
        self.play(Create(rects_right3))
        self.wait(4)
        self.play(FadeOut(rects_right3))
        self.play(Create(rects_right4))
        self.wait(4)
        self.play(FadeOut(rects_right4))
        self.play(Create(rects_right5))
        self.wait(4)
        self.play(FadeOut(rects_right5))
        self.play(Create(rects_right6))
        self.wait(4)


class bbb(Scene):
  
    def construct(self):
        txt1 = Title('Somas de Riemann')
        txt2 = Title('Somas de Riemann - Visualização')
        
        self.play(FadeIn(txt1))
        self.wait(0.5)
        self.play(Transform(txt1,txt2))
        self.wait()

        txt3 = Text('A seguir, teremos 1 exemplo de integral definida entre 0 e 3,').scale(0.6)
        txt4 = Text('nele, podemos observar o conceito por trás da').scale(0.6).next_to(txt3,DOWN)
        txt5 = Text('Soma de Riemann').scale(0.6).next_to(txt4,DOWN)
        txt6 = MathTex(r"A(a, b, f) = \int_{a}^{b} f(x) dx = \lim_{n \to \infty} \sum _{i=1} ^{n} f{\left( {a+i\frac{b-a}{n}} \right)} \frac{b-a}{n}")

        self.play(FadeIn(txt3,txt4,txt5))
        self.wait(6.5)
        self.play(FadeOut(txt3,txt4,txt5))
        self.wait(0.25)
        self.play(FadeIn(txt6))
        self.wait(16.5)
        self.play(FadeOut(txt6))
        self.wait(0.25)

        t1 = MathTex("Exemplo ~ 1: {x}+{1}").scale(0.9).next_to(txt1,DOWN)

        self.play(FadeIn(t1))

        ax = Axes(
            x_range=[-2, 5, 1],
            y_range=[0, 6, 1],
            tips=False,
            axis_config={"include_numbers": True}
        ).scale(0.8).next_to(txt1, DOWN, buff=1.2)
        graph1 = ax.plot(lambda x: x + 1, x_range=[-2, 5], use_smoothing=False)
        self.play(Create(ax))
        self.wait()
        self.play(Create(graph1))
        self.wait()
        
        rects = VGroup()

        rects_right1 = ax.get_riemann_rectangles(
            graph1,
            x_range=[0, 3],
            dx=1.5,
            color=(YELLOW_A, MAROON_A, BLUE_A, GREEN_A),
            input_sample_type="right",
        )
        rects_right2 = ax.get_riemann_rectangles(
            graph1,
            x_range=[0, 3],
            dx=1,
            color=(YELLOW_A, MAROON_A, BLUE_A, GREEN_A),
            input_sample_type="right",
        )
        rects_right3 = ax.get_riemann_rectangles(
            graph1,
            x_range=[0, 3],
            dx=0.05,
            color=(YELLOW_A, MAROON_A, BLUE_A, GREEN_A),
            input_sample_type="right",
        )
        rects_right4 = ax.get_riemann_rectangles(
            graph1,
            x_range=[0, 3],
            dx=0.025,
            color=(YELLOW_A, MAROON_A, BLUE_A, GREEN_A),
            input_sample_type="right",
        )

        self.play(Create(rects_right1))
        self.wait(5)
        self.play(FadeOut(rects_right1))
        self.play(Create(rects_right2))
        self.wait(4)
        self.play(FadeOut(rects_right2))
        self.play(Create(rects_right3))
        self.wait(4)
        self.play(FadeOut(rects_right3))
        self.play(Create(rects_right4))
        self.wait(4)
        self.play(FadeOut(rects_right4,graph1,ax,t1,txt1 ))
        self.wait()  


class ccc(Scene):
  
    def construct(self):
        txt1 = Title('Somas de Riemann')
        txt2 = Title('Somas de Riemann - Visualização')
        
        self.play(FadeIn(txt1))
        self.wait(0.5)
        self.play(Transform(txt1,txt2))
        self.wait()

        t1 = MathTex("Exemplo ~ 1: {x}+{1}").scale(0.9).next_to(txt1,DOWN)

        self.play(FadeIn(t1))

        ax = Axes(
            x_range=[-2, 5, 1],
            y_range=[0, 6, 1],
            tips=False,
            axis_config={"include_numbers": True}
        ).scale(0.8).next_to(txt1, DOWN, buff=1.2)
        graph1 = ax.plot(lambda x: x + 1, x_range=[-2, 5], use_smoothing=False)
        self.play(Create(ax))
        self.wait()
        self.play(Create(graph1))
        self.wait()
        
        rects = VGroup()

        rects_right1 = ax.get_riemann_rectangles(
            graph1,
            x_range=[0, 3],
            dx=1.5,
            color=(YELLOW_A, MAROON_A, BLUE_A, GREEN_A),
            input_sample_type="right",
        )
        rects_right2 = ax.get_riemann_rectangles(
            graph1,
            x_range=[0, 3],
            dx=1,
            color=(YELLOW_A, MAROON_A, BLUE_A, GREEN_A),
            input_sample_type="right",
        )
        rects_right3 = ax.get_riemann_rectangles(
            graph1,
            x_range=[0, 3],
            dx=0.75,
            color=(YELLOW_A, MAROON_A, BLUE_A, GREEN_A),
            input_sample_type="right",
        )
        rects_right4 = ax.get_riemann_rectangles(
            graph1,
            x_range=[0, 3],
            dx=0.5,
            color=(YELLOW_A, MAROON_A, BLUE_A, GREEN_A),
            input_sample_type="right",
        )
        rects_right5 = ax.get_riemann_rectangles(
            graph1,
            x_range=[0, 3],
            dx=0.25,
            color=(YELLOW_A, MAROON_A, BLUE_A, GREEN_A),
            input_sample_type="right",
        )
        rects_right6 = ax.get_riemann_rectangles(
            graph1,
            x_range=[0, 3],
            dx=0.125,
            color=(YELLOW_A, MAROON_A, BLUE_A, GREEN_A),
            input_sample_type="right",
        )
        rects_right7 = ax.get_riemann_rectangles(
            graph1,
            x_range=[0, 3],
            dx=0.06125,
            color=(YELLOW_A, MAROON_A, BLUE_A, GREEN_A),
            input_sample_type="right",
        )
        rects_right8 = ax.get_riemann_rectangles(
            graph1,
            x_range=[0, 3],
            dx=0.03,
            color=(YELLOW_A, MAROON_A, BLUE_A, GREEN_A),
            input_sample_type="right",
        )

        self.play(Create(rects_right1))
        self.wait(5)
        self.play(FadeOut(rects_right1))
        self.play(Create(rects_right2))
        self.wait(4)
        self.play(FadeOut(rects_right2))
        self.play(Create(rects_right3))
        self.wait(4)
        self.play(FadeOut(rects_right3))
        self.play(Create(rects_right4))
        self.wait(4)
        self.play(FadeOut(rects_right4))
        self.play(Create(rects_right5))
        self.wait(4)
        self.play(FadeOut(rects_right5))
        self.play(Create(rects_right6))
        self.wait(4)
        self.play(FadeOut(rects_right6))
        self.play(Create(rects_right7))
        self.wait(4)
        self.play(FadeOut(rects_right7))
        self.play(Create(rects_right8))
        self.wait(4)
        self.play(FadeOut(rects_right8,graph1,ax,t1,txt1 ))
        self.wait() # C-digos
