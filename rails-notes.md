# Rails Notes

- Why view files are named xxx.html.erb?

  Lets look at the following error message when we try to access a url without defining the view:

  > Missing template articles/new, application/new with {:locale=>[:en], **:formats=>[:html]**, :variants=>[], **:handlers=>[:erb, :builder, :raw, :ruby, :coffee, :jbuilder]**}. Searched in: \* "~/blog/app/views"

  This error message reveals a lot of useful information:

  1. There is a hash value `:formats=>[:html]`. This tells that rails is looking for an `html` template.
  2. There is a hash value `:handlers=>[:erb...]`. This tells that what handlers can be used to render the template. `erb` is one of the available template engines. So, the route can look for files end with `erb`

  Combining out findings, the file naming pattern xxx.html.erb is very logical. The Rails controll can use the file extention to determine the `handler` and `template` to use for rendering the view. 
