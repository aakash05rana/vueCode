<template>
    <div>
        <h1>Add a new Overhead</h1>
        <form method="POST" action="https://fbc.exitest.com/vendor/addFacility">
            <input type="text" id="fname" name="FacilityName" required="" placeholder="Facility Name.." />
            <br />
            <input type="text" id="lname" name="FacilityDescription" required="" placeholder="Facility Description.." />
            <input style="display: none" name="FacilityType" value="O" />
            <br />
            <label>Do you want to add vendor for this Facility?</label>
            <select name="Choice" required="">
                <option value="YES">Yes</option>
                <option value="NO">No</option>
            </select>
            <br />
            <br />
            <input type="submit" value="GO!" />
        </form>
    </div>
</template>
