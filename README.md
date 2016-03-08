# Validation-Control
Mandatory Text Control


function LV_validationControl(){

    setTimeout(function () {
        $("#divContent ").each(function () {
            if ($(".LV_validation_message").text() != "") {
                var temp = $(".LV_validation_message").text();
                var count = (temp.match(/\*/g) || []).length;
                $('#LV_validationControl .LV_validationControl').html(count);
            }
            if (count > 0) {
                $("#LV_validationControl").modal();
            }
        });
    }, 100);
    
    < form action="#" id="Form" >
        
         < div class="form-group">
                < input type="text" class="form-control" id="Name" placeholder="Name">
          </div >
            < script type="text/javascript">
                var NameVal = new LiveValidation('Name', { onValid: function () { } });
               NameVal.add(Validate.Presence, { failureMessage: '*Enter your name ' });
            </script >

             <div class="form-group">
                <input type="text" class="form-control" id="Surname" placeholder="Surname">
          </div>
            <script type="text/javascript">
                var SurnameVal = new LiveValidation('Surname', { onValid: function () { } });
               SurnameVal.add(Validate.Presence, { failureMessage: '*Enter your surname ' });
            </script>
        
        <div class="form-group">
                <input type="text" class="form-control" id="Password" placeholder="Password">
          </div>
            <script type="text/javascript">
                var PasswordVal = new LiveValidation('Password', { onValid: function () { } });
               PasswordVal.add(Validate.Presence, { failureMessage: '*Enter your password ' });
            </script>
        
        <input type="button" value="Send" onclick=" LV_validationControl(); $('#Form').submit()"> 
        </form>
