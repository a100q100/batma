==============================
Seu primeiro programa no Batma
==============================

.. contents:: Índice

Como todo projeto deve ter seu próprio *"Hello World"*, essa seção apresenta 
alguns exemplos básicos da utilização do Batma. Esse documento usa como base o 
template criado pelo Robi, você pode gerar o seu ou simplesmente copiar o 
seguinte trecho de código:

.. code-block:: python

    import batma

    class MyGame(batma.Game):
        def initialize(self):
            pass
        
        def load_content(self):
            pass

        def update(self, tick):
            pass
        
        def draw(self):
            pass

    game = MyGame()
    batma.run()


-----------
Hello World
-----------

1. Comece criando um novo arquivo chamado ``hello_world.py``, com o template 
   básico (citado no começo).
2. Nós vamos utilizar um ``Label``, elemento para exibição de texto. Como ele é 
   um elemento gráfico, é necessário criá-lo no método ``load_content``:

.. code-block:: python

    def load_content(self):
        self.label = batma.Label('Hello, World!', self.center)

Aqui criamos uma Label com o texto "Hello, World!" e a posição setada para o 
centro da janela.

3. Com o objeto criado, basta mandar desenhá-lo, isso é feito no método 
``draw``:

.. code-block:: python

    def raw(self):
        self.label.draw()

4. Agora basta executar o exemplo, rode ``python hello_world.py`` ou dois 
   cliques no windows.

Resultado:

.. image:: /_static/hello_world_batma.png
   :alt: Hello World com Batma
   :align: center
   :scale: 75%

:download:`Arquivo do exemplo: hello_world.py </_static/examples/hello_world.py>`


-------------
Hello Sprites
-------------

1. Crie um novo arquivo chamado ``hello_sprites.py``, com o template básico 
   (citado no começo).
2. Agora será criado um ``Sprite`` utilizando a imagem 
   :download:`python_logo.png </_static/python_logo.png>`. Salve essa imagem no 
   mesmo diretório do arquivo principal (Para mais informações sobre diretóricos
   dos recursos leia).

.. code-block:: python

    def load_content(self):
        self.sprite = batma.Sprite('python_logo.png', self.center)

O segundo argumento do sprite seta sua posição para o sentro da janela.

3. Com o objeto criado, basta mandar desenhá-lo, isso é feito no método ``draw``:

.. code-block:: python

    def draw(self):
        self.sprite.draw()

4. Agora basta executar o exemplo, rode ``python hello_world.py`` ou dois 
   cliques no windows.

Resultado:

.. image:: /_static/hello_sprites_batma.png
   :alt: Hello World exmaplo com sprite no Batma
   :align: center
   :scale: 75%

:download:`Arquivo do exemplo: hello_sprites.py </_static/examples/hello_sprites.py>`


--------------------
Primitivas e eventos
--------------------

Agora vamos utilizar duas funcionalidades do Batma: desenhar primitivas e tratar
eventos.

1. Crie um novo arquivo chamado ``primitives_events.py``, com o template básico 
   (citado no começo).
2. Dessa vez não será necessário carregar nenhum elemento, todas as funções do 
   módulo ``batma.draw`` desenha diretamente na tela, então:

.. code-block:: python

    def draw(self):
        batma.draw.circle(self.mouse.position, 40)

3. Execute o exemplo, você verá um círculo de raio 40 acompanhando a posição do 
   mouse.
4. Podemos melhorar o exemplo, vamos começar passando a posição e o raio do 
   círculo para uma varíavel:

.. code-block:: python

    def initialize(self):
        self.circle_position = (0, 0)
        self.circle_radius = 40

5. Agora vamos atualizar os valores dessas variáveis no método ``update``.

.. code-block:: python

    def update(self, tick):
        self.circle_position = self.mouse.position
        
        if self.keyboard[batma.keys.UP]:
            self.circle_radius += 1
        if self.keyboard[batma.keys.DOWN]:
            self.circle_radius -= 1

A cada chamada ao ``update`` a variável que guarda a posição do círculo 
(``self.circle_position``) é atualizada com a posição atual do mouse 
(``self.mouse.position``). Também é verificado se a tecla ``<UP>`` do teclado 
está sendo pressionada (``self.keyboard[batma.keys.UP]``), se estiver a variável 
que guarda o raio é atualizada (``self.circle_radius``), o mesmo acontece com a 
tecla ``<DOWN>``.

6. Agora atualize a chamada da função ``batma.draw.circle``:

.. code-block:: python

    def draw(self):
        batma.draw.circle(self.circle_position, self.circle_radius)

7. Execute o exemplo:

.. image:: /_static/primitives_events_batma.png
   :alt: Exemplo de uso de primitivas e eventos
   :align: center
   :scale: 75%

:download:`Arquivo do exemplo: primitives_events.py </_static/examples/primitives_events.py>`
