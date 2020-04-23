# Define UI for application that draws a plot of the approximate integral
ui <- fluidPage(

  # Application title
  titlePanel("Monte-Carlo Integration"),

  # Sidebar with text input for the function to integrate, numeric inputs for the range of integration and number of Monte-Carlo replications
  sidebarLayout(
    sidebarPanel(
      textInput("fun", "Function to integrate:","sin(10*x)*exp(cos(x))"),
      numericInput("low", "Integral lower bound:", 0, min = -100, max = 100),
      numericInput("up", "Integral upper bound:", 1, min = -100, max = 100),
      numericInput("B", "Number of Monte-Carlo replications:", 10^5,
                   min = 100, max = 10^9),
      actionButton("button", "Compute Integral")
    ),

    # Show a plot of the integrated area under the function
    mainPanel(
      plotOutput("distPlot")
    )
  )
)

# Define server logic required to draw the integration plot
server <- function(input, output) {

  a <- eventReactive(input$button, {
    mc_int(x_range = c(input$low, input$up),
           fun = input$fun, B = input$B)
  })

  output$distPlot <- renderPlot({
    plot(a())
  })

}

# Run the application
shinyApp(ui = ui, server = server)
