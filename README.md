# EasyGoogle

Welcome !

I do my best for you can take the easy way to adapt my code on yours.

The code is for VueJs but is can easy adjust for Js !

This is a Engine who you need !

	searchData(){

            /* Reinitialise mon résultat */
            this.preSearch = [];
            /* Entrer user + conversion Maj */
            const user = this.userEnter.toUpperCase();
            /* Convertit l'obj en array (jeux) */
            const arrayJeux = Object.values(this.jeux);
            arrayJeux.map((Game,index) => {	
						
                /* Prise des nom seul du jeux en cours d'itération */
                const nameGame = Game.name.toUpperCase();
                /* Pour chaque caractère du jeux */
                let save = '';
                let deleteItem = '';
                for (let i=0; i < user.length; i++){
                    
                    /* Caractère === Caractère Game */
                    if (user[i] === nameGame[i]){
                        save = Game.name;
                    }else {
                        deleteItem = Game.name
                        /* Pas égale = casse le boucle currGame */
                        break
                    }  
                }
                if (save === ''){
                    /* Dont push empty string */
                }else {
                   this.preSearch.push(save);  
                }

                for (let C=0; C < this.preSearch.length; C++){
                    if(deleteItem.toUpperCase() === this.preSearch[C].toUpperCase()){
                        const result = this.preSearch.findIndex(mot => mot === deleteItem.toUpperCase());
                        this.preSearch.splice(result,1)  ;
                    }
                }     
            });
        },
        
The First line is this preSearch = [] , so is an Array and inside you got the result ok ?

After you got "user = this.userEnter.toUpperCase()" is just a input who user Enter search is want

(toUpperCase is easy way to compare all in MAJ)

const arrayJeux = Object.values(this.jeux); You need to change that for me is a Object convert in array. 

You need arrayJeux = An Array

Now The html (vueJs)

	<input v-model="userEnter" @keyup="searchData()" type="text">
            <div v-if="userEnter !== ''" class="alert alert-info searchResult">
                <h2 class="myResult" v-for="(search,index) in preSearch">{{ search }}</h2>
            </div>
            
If Keyup is execute my function searchData and my first array preSearch is distribut in v-for boucle in <h2>    

You now all ! So do it :)        
