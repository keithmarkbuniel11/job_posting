<template>
    <div>
             <h1>Job posting Listing</h1>
        <table class="table table-hover">
            <thead>
                <tr>
                <th>job name</th>
                <th>job description</th>
                <th>job vacants</th>
                <th>Actions</th>
                </tr>
            </thead>
            <tbody>
                <tr>
                    <td>Sr. Programmer</td>
                    <td>lead a developer</td>
                    <td>2</td>
                    <td><button class="btn btn-secondary btn-sm"><i class="fa fa-edit"></i></button>
                        <button class="btn btn-danger btn-sm"><i class="fa fa-trash"></i></button>
                    </td>
                </tr>
            </tbody>
            <tfoot>
              <tr>
                  <td>
                      <div class="form-group">
                          <input type="text" class="form-control" placeholder="Input Job Name" v-model="form.job_name">
                      </div>
                  </td>
                  <td>
                      <div class="form-group">
                          <input type="text" class="form-control" placeholder="Input Job Description" v-model="form.job_description">
                      </div>
                  </td>
                  <td>
                      <div class="form-group">
                          <input type="number" class="form-control" placeholder="Input Job Vacants" v-model="form.job_vacants">
                      </div>
                  </td>
                  <td>
                      <div class="form-group">
                          <button class="btn btn-primary btn-sm" @click="submit"><i class="fa fa-plus"></i></button>
                      </div>
                  </td>
              </tr>
            </tfoot>
    </table>
    </div>
</template>


<script>
export default {
    data(){
        return{
            form: {
                job_name: null,
                job_description: null,
                vacants: 0
                 
            }
        }
    },
    methods: {



        submit(){
            
            axios.post('/job_postings',this.form) 
            .then(function (response) {
                alert('success');
            })
            .catch(function (error) {
                alert('Something went wrong');
            });
        }
    }
}
</script>

