# HtmlTable

##Install-Package HtmlTable

###Doc in Dev...
```C#
@model IEnumerable<HtmlTable.Tests.ViewModel.UsuarioViewModel>

@{
    ViewBag.Title = "Index";
}

<script>
    function customCommand(e) {
        console.log(e);
        alert("customCommand");
    }

    function customCommand2(e) {
        console.log(e);
        alert("data-idusuario: " + $(e).attr('data-idusuario') +
                "|" + "data-datanascimentousuario: " + $(e).attr('data-datanascimentousuario'));
    }
</script>

<hr />
<h2>Index</h2>

<p>
    @Html.ActionLink("Create New", "Create")
</p>

@(Html.TableFor(Model)
    .ForMember(c => c.EmailUsuario)
    .ForMember(c => c.DataNascimentoUsuario, AlignType.Center)
    .TableBordered()
    .TableCondensed()
    .TableHover()
    .TableResponsive()
    .TableStriped()
    .IconStyle(TableIconStyle.FontAwesome)
    .Edit("Editar", "Editar", "Usuario", "fa fa-bolt")
    .Command("CustomExample", "customCommand(this)", null, "btn-primary", "fa fa-cog", c =>  c.IdUsuario )
    .Command("CustomExample2", "customCommand2(this)", null, "btn-default", "fa fa-cog", c => new { c.IdUsuario, c.DataNascimentoUsuario })
)
```
