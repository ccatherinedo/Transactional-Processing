# Transactional-Processing
advancing the mock replica patient form for a 24 hour emergency clinic service by utilizing javascript, html, css

<!DOCTYPE html>
<!--
    Program Name: patient-form.html (homework1.html)
    Name: Catherine Do'
    Date created: 9/18/2024
    Date last updated:
    Version: 1.0
    Purpose: Homework 1 HTML Form
-->
<html lang="en">
    <head>
        <link rel="stylesheet" href="homework2-patient-form.css"> <!--linkd and brings to the css file-->
       
        <title>New Patient Account Sign Up | Around the Clock Emergency Clinic</title>      <!--showcased text title in the browser's tab-->
    </head>
    <body>
        <header>    <!--the top portion of the page that encapsulates the logo, title of the website, and today's date -->
            <table width="100%>
            <tr>
                <td valign="top" align="left" width="20%">
                    <div class="image">
                        <img align="center" src="emergencycliniclogo1.png" alt="Around The Clock Emergency Clinic Logo" width="70px" id="logo"/>
                    </div>    
                </td>


                <td>
                    <h2> Around The Clock Emergency Clinic</h2>
                </td>
               
                <td valign="bottom" align="right" width="20%">
                   <p> Today's Date: <span id="today"></span></p>   <!-- calls for the current date-->
                    
                </td>


            </tr>
            </table>
        </header>
<hr>
<!-- patient registration form begins here-->
<form name ="signup" id = "signup" action="thankyou.html">   <!--directs to the ending thank you page-->
    <center>
        <div class="format">
            <table>
                <tr>
                    <th colspan="4">Sign Up For A Patient Portal Account</th>
                </tr>
                <!--user's fill-in information section of form starts here-->

            
                <tr>
                    <td class="td1"><label for="first">First Name:</label></td>
                    <td>
                        <input
                        type="text"
                        name="first"
                        id="first"
                        maxlength="30"
                        required
                        title="Input letters, apostrophes, and dashes only"
                        pattern="[a-zA-Z']{1,30}"
                        onblur="validateFirst()"
                        placeholder="Jane"
                        />
                        
                    </br>
                    <span class="error" id="first-error"></span>

                    </td>
                </tr>


                <tr>
                    <td class="td1"><label for="mint">Middle Initial:</label></td>
                    <td>
                        <input
                        type="text"
                        name="mint"
                        id="mint"
                        maxlength="1"
                        title="Input alphabetical values only"
                        pattern="[a-zA-Z']{0,1}"
                        onblur="validateMint()"
                        placeholder="B"
                        />
                    </br>
                    <span class="error" id="mint-error"></span>
                    </td>
                </tr>


                <tr>
                    <td class="td1"><label for="last">Last Name:</label></td>
                    <td>
                        <input
                        type="text"
                        name="last"
                        id="last"
                        maxlength="30"
                        required
                        title="Input letters, apostrophes, and dashes only"
                        pattern="[a-zA-Z']{1,30}"
                        onblur="validateLast()"
                        placeholder="Doe"
                        />
                    </br>
                    <span class="error" id="last-error"></span>
                    </td>
                </tr>


                <!-- 3 radio buttons!-->

                <tr>
                    <td class="td1"><label for="pgender">Patient's Gender</label></td>
                    <td>
                        <input
                        type="radio"
                        id="s1"
                        name="pgender"
                        value="Female"
                        />
                        Female
                       
                        <input
                        type="radio"
                        id="s2"
                        name="pgender"
                        value="Male"
                        />
                        Male


                        <input
                        type="radio"
                        id="s3"
                        name="pgender"
                        value="Nonbinary"
                        />
                        Nonbinary


                    </td>
                </tr>

                    <!-- date in mm/dd/yyyy format-->
                <tr>
                    <td class="td1"><label for="birthday">Date of Birth:</label></td>
                    <td>
                        <input
                        type="date"
                        id="birthday"
                        name="birthday"
                        onblur="validateBirthday()"
                        required
                        />
                    </br>
                    <span class="error" id="birthday-error"></span>
                    </td>
                </tr>

                <!-- makes the filled in answer obscured and hidden-->
                <tr>
                    <td class="td1"><label for="ssn">SSN:</td>
                        <td>
                            <input
                            type="password"
                            minlength="9"
                            maxlength="11"
                            name="ssn"
                            id="ssn"
                            required
                            title="Input only numerical values"
                            placeholder="XXX-XX-XXXX"
                            onblur="validateSsn()"
                            />
                        </br>
                        <span class="error" id="ssn-error"></span>
                        </td>
                </tr>

                <tr>
                    <th colspan="4"><hr></th>
                </tr>
                    <!-- end of first section in the form, adding in a distinct end with a divider-->

                <tr>
                    <th colspan="4">Patient's Contact Information</th>
                   
                <tr>

                    <!-- taking residence and mailing information section-->
                    <tr>
                        <td class="td1"><label for="address1">Home Address:</label></td>
                        <td>
                            <input
                            type="text"
                            name="address1"
                            id="address1"
                            maxlength="30"
                            required
                            title="Enter in Your Main Home Address"
                            placeholder="321 Sesame Street"
                            onblur="validateAddress1()"
                            />
                        </br>
                        <span class="error" id="address1-error"></span>
                        </td>
                    </tr>


                    <tr>
                        <td class="td1"><label for="address2">Mailing Address:</label></td>
                        <td>
                            <input
                            type="text"
                            name="address2"
                            id="address2"
                            maxlength="30"
                            required
                            title="Enter in Your Mailing Address"
                            placeholder="22 Jump Street"
                            />
                        </td>
                    </tr>


                    <td class="td1"><label for="city">City:</label></td>
                    <td>
                        <input
                        type="text"
                        name="city"
                        id="city"
                        maxlength="30"
                        required
                        title="Enter in your City of Residence"
                        placeholder="Zootopia"
                        />
                    </td>
                </tr>

                <!-- dropdown box list-->
                <tr>
                    <td class="td1"> <label for="state">State:</label></td>
                        <td>
                            <select>
                            <option selected disabled>Choose a State Selection</option>
                            <option value="AL">Alabama</option>
                            <option value="AK">Alaska</option>
                            <option value="AZ">Arizona</option>
                            <option value="AR">Arkansas</option>
                            <option value="CA">California</option>
                            <option value="CO">Colorado</option>
                            <option value="CT">Connecticut</option>
                            <option value="DE">Delaware</option>
                            <option value="DC">District Of Columbia</option>
                            <option value="FL">Florida</option>
                            <option value="GA">Georgia</option>
                            <option value="HI">Hawaii</option>
                            <option value="ID">Idaho</option>
                            <option value="IL">Illinois</option>
                            <option value="IN">Indiana</option>
                            <option value="IA">Iowa</option>
                            <option value="KS">Kansas</option>
                            <option value="KY">Kentucky</option>
                            <option value="LA">Louisiana</option>
                            <option value="ME">Maine</option>
                            <option value="MD">Maryland</option>
                            <option value="MA">Massachusetts</option>
                            <option value="MI">Michigan</option>
                            <option value="MN">Minnesota</option>
                            <option value="MS">Mississippi</option>
                            <option value="MO">Missouri</option>
                            <option value="MT">Montana</option>
                            <option value="NE">Nebraska</option>
                            <option value="NV">Nevada</option>
                            <option value="NH">New Hampshire</option>
                            <option value="NJ">New Jersey</option>
                            <option value="NM">New Mexico</option>
                            <option value="NY">New York</option>
                            <option value="NC">North Carolina</option>
                            <option value="ND">North Dakota</option>
                            <option value="OH">Ohio</option>
                            <option value="OK">Oklahoma</option>
                            <option value="OR">Oregon</option>
                            <option value="PA">Pennsylvania</option>
                            <option value="PR">Puerto Rico</option>
                            <option value="RI">Rhode Island</option>
                            <option value="SC">South Carolina</option>
                            <option value="SD">South Dakota</option>
                            <option value="TN">Tennessee</option>
                            <option value="TX">Texas</option>
                            <option value="UT">Utah</option>
                            <option value="VT">Vermont</option>
                            <option value="VA">Virginia</option>
                            <option value="WA">Washington</option>
                            <option value="WV">West Virginia</option>
                            <option value="WI">Wisconsin</option>
                            <option value="WY">Wyoming</option>
                        </select>
                    </td>
                </tr>
                <tr>
                    <td class="td1"><label for="zip">ZipCode:</label></td>
                    <td>
                        <input
                        type="text"
                        name="zip"
                        id="zip"
                        maxlength="5"
                        pattern="[0-9]{5}"
                        title="Input numerical values only"
                        placeholder="XXXXX"
                        required
                        pattern="[0-9]{5}"
                        onblue="validateZip()"
                        />
                    </br>
                    <span class="error" id="zip-error"></span>
                     </td>
                </tr>


                </tr>
                    <td class="td1"><label for="email">Email Address:</label></td>
                    <td>
                        <input
                        type="text"
                        name="email"
                        id="email"
                        title="Enter Your Email"
                        placeholder="appleid@hotmail.com"
                        required
                        pattern="[a-z0-9._%+-]+@[a-z0-9.-]+\.[a-z]{2,20}$"
                        onblur="validateEmail()"
                        />
                    </br>
                    <span class="error" id="email-error"></span>
                     </td>
                </tr>


                </tr>
                    <td class="td1"><label for="celly">Phone Number:</label></td>
                    <td>
                        <input
                        type="text"
                        name="celly"
                        id="celly"
                        maxlength="12"
                        pattern="[0-9]{3}-[0-9]{3}-[0-9]{4}"
                        title="Please Enter Your Phone Number"
                        placeholder="XXX-XXX-XXXX"
                        required
                        onblur="validateCelly()"
                        />
                    </br>
                    <span class="error" id="celly-error"></span>
                     </td>
                </tr>


                <tr>
                    <th colspan="4"><hr></th> <!-- another divider-->
                </tr>


                <!--patient history section of form-->
                <tr>
                    <th colspan="4">Patient's Medical History</th>
                </tr>

                    <!-- checkbox element-->
                <tr>
                    <td class="td1"><label for="med_history">Check off what symptons you are experiencing:</label></td>
                    <td>
                        <input type="checkbox" id="optionl" value="Headache"/>
                        <label for="Headache">Headache</label><br>


                        <input type="checkbox" id="option2" value="Nausea"/>
                        <label for="Nausea">Nausea</label><br>


                        <input type="checkbox" id="option3" value="Fever"/>
                        <label for="Fever">Fever</label><br>


                        <input type="checkbox" id="option4" value="Loss of Appetite"/>
                        <label for="Loss of Appetite">Loss of Appetite</label><br>


                        <input type="checkbox" id="option5" value="Diarrhea"/>
                        <label for="Diarrhea">Diarrhea</label><br>


                        <input type="checkbox" id="option6" value="Body Pains"/>
                        <label for="Body Pains">Body Pains</label><br>


                        <input type="checkbox" id="option7" value="Infections"/>
                        <label for="Infections">Infections</label><br>


                        <input type="checkbox" id="option8" value="Other" />
                        <label for="Other">Other</label>
                    </td>
                </tr>

                <!-- text area to describe something for input  -->
                <tr>
                    <td class="td1" align="right">
                        <label for="notes">If you selected any of the above, please provide further explanation:</label>
                    </td>
                    <td>
                        <textarea
                        rows="5"
                        cols="60"
                        maxlength="450"
                        id="notes"
                        name="notes"
                        title="Please enter a brief description for your visit"
                        placeholder="(Insert text here....)"
                        ></textarea>
                        <span id="description_text"></span>
                    </td>
                </tr>


                <!--html for the slide bar-->
                <tr>
                    <td class="td1"><label for="range">Urgency of Appointment Visit? <br/>(Rate on a scale from 1 to 10)</label></td>
                    <td>
                        <input
                        type="range"
                        name="range"
                        id="range"
                        min="1"
                        max="10"
                        value="0"
                        />
                        <span id="range-slider"></span>
                    </td>
                </tr>


                <tr>
                    <th colspan="4"><hr></th>
                </tr>


                <!--account information login begins here-->
                <tr>
                    <th colspan="4">Finish Creating Patient Portal Account:</th>
                </tr>

                <!-- textbox for userid-->
                <tr>
                    <td class="td1"><label for="user">Username:</label></td>
                    <td>
                        <input
                        type="text"
                        name="user"
                        id="user"
                        minlength="7"
                        maxlength="20"
                        required
                        title="Username must contain at least 7 characters and cannot start with a numerical value"
                        placeholder="janebdoewins"
                        onblur="validateUser()"
                        />
                    </br>
                    <span class="error" id="user-error"></span>
                    </td>
                </tr>

        
                <tr>
                    <td class="td1"><label for="passw">Password:</label></td>
                    <td>
                        <input
                        type="password"             
                        name="passw"
                        id="passw"
                        minlength="7"
                        maxlength="30"
                        required
                        title="Password must contain at least 10 characters, 1 uppercase letter, 1 lowercase letter, 1 number, and 1 special character"
                        placeholder="Required*"
                        onblur="validatePassw()"
                        oninput="validatePassw()"
                        onfocus="validatePassw()"
                        />
                    </br>
                    <span class="error" id="passw-error"></span>
                    </td>
                </tr>
                        <!--obscuring user input-->

                <tr>
                    <td class="td1"><label for="check_passw">Confirm Password:</label></td>
                    <td>
                        <input
                        type="password"
                        name="check_passw"
                        id="check_passw"
                        minlength="7"
                        maxlength="30"
                        required
                        title="Please re-enter the password"
                        placeholder="Required*"
                        onblur="confirmPassw()"
                        oninput="confirmPassw()"
                        onfocus="confirmPassw()"
                        />
                    </br>
                    <span class="error" id="passw-error"></span>
                    </td>
                </tr>


                <tr>
                    <td class="td1" colspan="4">
                        <center>
                            <input type="submit" name="submit" id="submit" style="font-family:'Courier New', Courier, monospace";>
                            <input type="reset" name="reset" id="reset" style="font-family:'Courier New', Courier, monospace";>
                            <input type="button" name="review" id="review" value="Review" style="font-family:'Courier New', Courier, monospace"; onclick="reviewInput()">
                        </center>
                    </td>
                </tr>




            </table>
        </div>
    <div class="pword-message">
        <span id="msg1"></span><br/>
        <span id="msg2"></span><br/>
        <span id="msg3"></span><br/>
        <span id="msg4"></span><br/>
        <span id="msg5"></span><br/>
        <span id="msg6"></span><br/>
        <span id="msg7"></span><br/>
        <span id="pword2-error"></span><br/>
        </div>
            <center>
                <p id="showInput"></p>
            </center>
    </div>
    </center>
</form>
<!-- footer goes here with website link-->
 <footer>
    <p id="footer">  &#169 2024 Around The Clock Emergency Clinic   | <a href="https://theuselessweb.com/" target="_blank" rel="noopener noreferrer"> Get In Touch With Us!</a></p>
 </footer>
 <script src="homework2.js"></script>
    </body>
</html>
