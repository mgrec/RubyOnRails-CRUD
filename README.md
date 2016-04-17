# RubyOnRails

## Ma première expérience avec Ruby On Rails

###### ETAPE 1 : Réalisation d'un CRUD basique

Génération de l'architecture du projet avec :

``` rails new "app name" ```

Pour lancer notre serveur nous utiliserons :

``` bin/rails server ```

La page par défaut sera alors :

``` http://localhost:3000/ ```


###### ETAPE 1 - A) CRUD : CREATE


Mon controller pour les utilisateurs :

__users_controller.rb__


``` ruby
class UsersController < ApplicationController
  def new
  end

  def create
    @user = User.new(user_params)
    @user.save
    redirect_to @user
  end

  private
    def user_params
    params.require(:user).permit(:name, :lastname, :description)
  end
end
```


###### ETAPE 1 - B) CRUD : READ


Mon controller pour les utilisateurs (ajout du READ) :

__users_controller.rb__


``` ruby
class UsersController < ApplicationController
  def index
    @users = User.all
  end

  def show
    @user = User.find(params[:id])
  end

...

end

```

###### ETAPE 1 - C) CRUD : UPDATE


Mon controller pour les utilisateurs (ajout du UPDATE) :

__users_controller.rb__


``` ruby
class UsersController < ApplicationController

...

  def edit
    @user = User.find(params[:id])
  end

  def update
  @user = User.find(params[:id])

...

end


```
