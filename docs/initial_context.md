

Give an architectural overview of a fastapi application using simple server-side rendering (see down for options) . Important is that the server should have distinct projects each one with a particular "presentation/presenter" module. These should be pluggable. A Noctiluca instance can have different projects. A "presentation/presenter" module can be used by different projects. A projects can one refer to one "presentation/presenter" module. 

Let's call the module a  "Glow" (type of Glow) which defines the visual / data behaviour. 
A Glow defines a data model and actions which interact with the model and will dynamically change the view of presenter and presentation. 

So a "slide Glow" with the idea to present "slides" coudl consist of 

1) a Presentation which consist of a visualisation of different slides which are objects with markdown in the datamodel
2) a presenter which shows the names  and description (perhaps the presentation in minimized form? and a home/end/next/prev buttons. They can be used to show the 
3) a datamodel. The model can be provided for by  use a large yaml or json file as the datamodel instantiation. 


Note that Based on the Use case and description it should be obvious that an action on the Presenter should not just be saved to the datamodel, but rather also directly synchronized to the presentation devices. So let's add to the requirement

A project can be opened on a presenter device. This device can start a "show". This will generate a show ID. This show will be accessible from any device by going to the /projects/<project_id>/ url which shows a view where the user can fill in the sjhow id in order to access it. Alternatively, people can directly access /projects/<project_id>/<show_id>

There should NOT be a /projects/<project_id>/presentation url

The presenter can access the correct presenter with /projects/<project_id>/ and a configured password. 

For each change to the data_model (e.g. changing the activeslide) all connected clients should automatically update the view, reflecting the change in the datamodel

Give me the architecture of this application. Use Python and FastAPIO and niceGUI as UI presentation 