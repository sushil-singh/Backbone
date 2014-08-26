Backbone
========
// Model Fetch
App.models.User = new UserModel();
App.models.User.fetch({
    data: {
        id: 1
    },
    success: (function () {
        console.log(' Service request success: ');
    }),
    error: (function (e) {
        console.log(' Service request failure: ' + e);
    }),
    complete: (function (e) {
        console.log(' Service request completed ');
    })
});

// Remove a view completely
destroy_view: function() {

    // COMPLETELY UNBIND THE VIEW
    this.undelegateEvents();

    this.$el.removeData().unbind(); 

    // Remove view from DOM
    this.remove();  
    Backbone.View.prototype.remove.call(this);

}
// http://stackoverflow.com/questions/7379263/disposing-of-view-and-model-objects-in-backbone-js

// http://workshop.unspace.ca/post/67567663306/avoiding-memory-leaks-in-backbone-js

// https://github.com/powmedia/backbone-deep-model
