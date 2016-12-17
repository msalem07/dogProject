Dog = function(){
		var self = this;
    
    self.name = ko.observable();
    self.gender = ko.observable();
    self.id = ko.observable();
    self.titles = ko.observable();
    
    self.validationObject = ko.validatedObservable({
    		name: self.name.extend({required: true}),
        gender: self.gender.extend({required:true}),
        id: self.id.extend({required: true}),
        titles: self.titles.extend({required:true})
    });
};

IndexViewModel = function () {

    var self = this;
    // observables
    self.users = ko.observableArray();
    self.name = ko.observable();

    // functions
    self.addUser = function () {
    	self.users.push(new Dog());
    };
		
    // validation
    self.validationObject = ko.validatedObservable({
        users: self.users,
        name: self.name.extend({
            required: true
        })
    });
    
    self.showErrors = function(){
    	self.validationObject.errors.showAllMessages();
    };
    
    //==========================================
    self.typeOfForm = ko.observable("");
    
    (function(){
    	 for(var i = 0; i < 8; i++)
       	self.users.push(new Dog());
    })();
};

ko.validation.init({
    grouping: {
        deep: true,
        live: true,
        observable: true
    }
});
var indexViewModel = new IndexViewModel();
ko.applyBindings(indexViewModel);
