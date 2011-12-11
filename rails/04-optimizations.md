!SLIDE

# Quelques optimisations

!SLIDE small

# app/controllers/users\_controller.rb

    @@@ ruby
    class UsersController < ApplicationController
      before_filter :get_user

      def show
        respond_with @user
      end

      private
      def get_user
        id = params[:id] || params[:user_id]
        if id
          @user = User.find params[:id]
        end
      end
    end

!SLIDE small

# app/views/users/\_form.html.erb

    @@@ erb
    <%= form_for user do |f|
        <%= f.text_field :username %>
        <%= f.submit %>
    <% end %>

!SLIDE small

# app/views/users/(new|edit).html.erb

    @@@ erb
    <%= render :partial => 'users/form',
        :locals => {:user => @user} %>
