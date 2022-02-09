<template>
    <div class="user_information">
        <div class="user_info_item">
            <h4>Personal</h4>
            <div class="user_info_base base-half">
                <label for="">Name</label>
                <div class="d_user_info_index">{{user.personal.name}}</div>
            </div>
            <div class="user_info_base base-half">
                <label for="">Birthdate</label>
                <div class="d_user_info_index">{{user.personal.birthdate}}</div>
            </div>
            <div class="user_info_base">
                <label for="">Address</label>
                <div class="d_user_info_index">{{user.personal.address}}</div>
            </div>
            
        </div>
        <div class="user_info_item">
            <h4>Education</h4>
            <div class="user_info_base base-half">
                <label for="">Birthdate</label>
                <div class="d_user_info_index">{{user.education.school}}</div>
            </div>
            <div class="user_info_base base-half">
                <label for="">Teacher</label>
                <div class="d_user_info_index">{{user.education.teacher}}</div>
            </div>
        </div>
        <div class="user_info_item">
            <h4>Evaluation</h4>
        </div>
        <div class="user_info_item">
            <h4>In case of emergency</h4>
            <div class="user_info_base base-half">
                <label for="">Name</label>
                <div class="d_user_info_index">{{user.guardian.name}}</div>
            </div>
            <div class="user_info_base base-half">
                <label for="">Relationship</label>
                <div class="d_user_info_index">{{user.guardian.relationship}}</div>
            </div>
            <div class="user_info_base">
                <label for="">Contact Number</label>
                <div class="d_user_info_index">{{user.guardian.contect_number}}</div>
            </div>
            <div class="user_info_base">
                <label for="">Address</label>
                <div class="d_user_info_index">{{user.guardian.address}}</div>
            </div>
            
            
        </div>
    </div>
</template>

<script>
export default {
    data(){
        return {
            user: {
                "personal": {
                    "name": 'Jonhn Peter Doe',
                    "address": 'Sample address, sample barangay, sample city, sample country',
                    "birthdate": 'January 01, 2021'
                },
                "guardian": {
                    "name": 'Josephen Doe',
                    "address": 'Sample address, sample barangay, sample city, sample country',
                    "contect_number": '(082) 123 3456',
                    "relationship": 'Mother'
                },
                "education": {
                    "school": 'Sample Elementary School',
                    "teacher": 'Sample Teacher',
                },
                "evaluations": {

                }
            }
        }
    }
}
</script>

<style scoped>
    .user_info_item {
        margin-bottom: 15px;
    }
    .user_info_item .user_info_base {
        font-size: 14px;
        margin-bottom: 10px;
    }
    .user_info_item .user_info_base.base-half {
        display: inline-block;
        width: 49%;
    }
    .user_info_item .user_info_base .d_user_info_index {
        font-size: 14px;
        font-weight: bold;
    }
    .user_info_item h4 {
        background: #ccc;
        font-weight: 400;
        font-size: 16px;
        line-height: 1em;
        padding: 10px 15px;
        margin-bottom: 10px;
        border-radius: 5px;
    }
</style>