# Rails_Checkbox_InAList
在一组数据中，进行多条check box选中操作，然后提交


http://apidock.com/rails/ActionView/Helpers/FormTagHelper/check_box_tag

Pass id collections with check box tags

It can be useful to pass a collection of ids to a controller, especially in the case of a has_many relationship, for example:

User has_many Roles
In your view you could have something like:

<ul>
  <% @roles.each do |role| %>
      <li>
        <%= check_box_tag 'role_ids[]', role.id -%>
        <%= h role.name -%>
      </li>
  <% end %>
</ul>
Note the square brackets after role_ids - this is important for passing a collection through to the controller.

If you place this in a form and submit it, you can expect to see a param passed into the controller that looks like:

"role_ids"=>["1", "2", "3"]
