# Prac1-Micro
\documentclass[a4paper,10pt]{article} 
\input{Config_files/config.tex} 
\pagestyle{empty}

\begin{document} 


\AddToShipoutPicture{\BackgroundPic}

\begin{center}

\includegraphics[width=0.9\linewidth]{Config_files/imagotipo.png}
\Huge
\textbf{Report \#1: Dado Digital}\\
\vspace{0.5cm}
\huge 
Alan Rendon D.
\color{black}
\end{center}

\begingroup
\LARGE
\noindent\textbf{Department:} Ingeniería Cibernética y Sistemas Computacionales\\
\textbf{Course:} Laboratorio de microcontroladores \\
\textbf{Instructor:} Benito Granados-Rojas, MSc.\\
\textbf{Date:} \today

\endgroup

%-------------------------

\Large
\section*{Abstract}
\color{black} La práctica consistía en simular un dado digital utilizando Proteus y MPLAB, utilizando el microcontrolador PIC16F628A. Nuestro objetivo era realizar un circuito con un display que mostrara números decimales enteros únicamente en el intervalo cerrado (1,6) y con el microcontrolador debía  contar con una entrada operada por botón, la cuenta regresiva debe ocurrir únicamente mientras se mantiene pulsado el botón y al liberar el botón, la cuenta debe detenerse en el dígito que está presente en el puerto en ese momento.

\newpage
\color{black}
\section{Introduction}
\color{black} Usaremos el microcontrolador PIC16F628A de la familia PIC creado por Microchip Technology Inc. Los PIC son una familia de microcontroladores tipo RISC y derivados del PIC1650, originalmente desarrollado por la división de microelectrónica de General Instrument. Un PIC es un circuito integrado programable (Programmable Integrated Circuited), el cual contiene todos los componentes para poder realizar y controlar una tarea, por lo que se denomina un microcontrolador. Utilizando un convertidor BCD a 7SEG y un display LED de 7 Segmentos(\cite{MPLAB_wiki}). \\
\\
Usaremos Proteus, en donde montaremos nuestro circuito. Proteus es un software de automatización de diseño electrónico, desarrollado por Labcenter Electronics Ltd., que consta de los dos programas principales: Ares e Isis, y los módulos VSM y Electra. En donde montaremos nuestro circuito(\cite{Proteus_Design_Suite_wiki}). \\
\\
Después cargaremos un código realizado en MPLAB. MPLAB es un editor IDE gratuito, destinado a productos de la marca Microchip. Este editor es modular, permite seleccionar los distintos microcontroladores soportados, además de permitir la grabación de estos circuitos integrados directamente al programador. \\Este codigo se hizo con el lenguaje ensamblador o assembly (en inglés: assembly language y la abreviación asm) es un lenguaje de programación de bajo nivel(\cite{Lenguaje_ensamblador_wiki}).
\\
Consiste en un conjunto de mnemónicos que representan instrucciones básicas para los computadores, microprocesadores, microcontroladores y otros circuitos integrados programables. Implementa una representación simbólica de los códigos de máquina binarios y otras constantes necesarias para programar una arquitectura de procesador y constituye la representación más directa del código máquina específico para cada arquitectura legible por un programador.




\newpage
\section{Procedures and Results}
    \subsection{Simulación en proteus}
        \color{black} Empezamos conectando los componentes
Microncontrolador PIC16F628A, convertidor BCD a 7 segmentos, display LED de 7 segmentos, switch, fuente de 5V, resistores (220Ω– 10kΩ)

\begin{figure}[H]
    \centering
    \includegraphics[scale=0.4]{Circuito1.PNG}
    \caption{Circuito en Proteus}
    \label{Circuito}
    \end{figure}


\color{black}\\Cargamos en el chip el programa de MPLAB, con las salidas del puerto B vamos a convertir  un BCD entonces sus salidas van al display de 7 segmentos, después con los 4 bits menos significativos para la salida del puerto B y el menos del puerto A para la señal de switch. Y establecemos una frecuencia para trabajar.\\
Se empieza la simulación con el switch cerrado empiezan a correr los números 6-5-4-3-2-1 y si se abre el switch se detiene donde se quedo hasta que se vuelva a cerrar el switch.


\newpage
    \subsection{Simulación en mplab}
        \color{black}El programa lo que hace cuando el switch está cerrado es ir decrementando una variable auxiliar de una cadena de 6 bits que se encuentra e n binario. Para evitar que se salga el 0, carga el 6 en el puerto B justo cuando llega a 0. Y cuando el switch se abre él se detiene en el número en que se haya quedado.


\section{Conclusions}
\color{black} Tuvimos los resultados que esperábamos, logrando la simulación y con esta pudimos concluir en que la practica nos ayudo a entender como se realiza una simulación, porque al comprender como el circuito y el código trabajan juntos o individualmente. Al trabajar con el lenguaje ensamblador comprendimos sus funciones y también entendimos mejor como es que trabaja el PIC16F628A y sus puertos.
\color{black}

\section{Repository}
\noindent
\url{https://github.com/alanrend0n/Prac1-Micro}

\section{Bibliography}
\printbibliography



\end{document}
