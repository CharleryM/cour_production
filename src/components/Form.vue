<template>
    <div class="expense-form">
      <h2>Ajouter une dépense</h2>
  
      <label for="expense-type">Type de dépense</label>
      <select id="expense-type" v-model="form.expenseType" class="form-select">
        <option value="Nourriture">Nourriture</option>
        <option value="Logement">Logement</option>
        <option value="Transport">Transport</option>
        <option value="Divertissement">Divertissement</option>
        <option value="Autre">Autre</option>
      </select>
  
      <label for="amount">Montant</label>
      <input type="number" id="amount" v-model="form.amount" class="form-input" placeholder="Montant en €" />
  
      <div style="display: flex;">
        <label for="isIncome">Type</label>
        <div class="form-switch">
            <input type="checkbox" v-model="form.isIncome" id="isIncome" />
            <span>{{ form.isIncome ? "Gain" : "Dépense" }}</span>
        </div>
    </div>
  
      <label for="date">Date</label>
      <input type="date" id="date" v-model="form.date" class="form-input" />
  
      <label for="reason">Raison</label>
      <input type="text" id="reason" v-model="form.reason" class="form-input" placeholder="Pourquoi cette dépense ?" />
  
      <label for="comment">Commentaire (facultatif)</label>
      <div class="form-switch">
        <input type="checkbox" v-model="form.isComment" id="comment-checkbox" />
        <span>{{ form.isComment ? "Non" : "Oui" }}</span>
      </div>
      <textarea v-if="!form.isComment" id="comment" v-model="form.comment" class="form-textarea" placeholder="Détails supplémentaires"></textarea>
  
      <label for="payment-method">Mode de paiement</label>
      <select id="payment-method" v-model="form.paymentMethod" class="form-select">
        <option value="credit-card">Carte de crédit</option>
        <option value="cash">Espèces</option>
        <option value="bank-transfer">Virement</option>
      </select>
  
      <button @click="submitForm" class="submit-button">Ajouter la dépense</button>
    </div>
  </template>
  
  <script>
  export default {
    name: 'form_dep',
    data() {
      return {
        form: {
          expenseType: '',
          amount: 0,
          isIncome: false,
          isComment: false,
          date: '',
          reason: '',
          comment: '',
          paymentMethod: '',
        },
      };
    },
    methods: {
      submitForm() {
        console.log('Données du formulaire:', this.form);
      },
    },
  };
  </script>
  
  <style scoped>
  .expense-form {
    display: flex;
    flex-direction: column;
    max-width: 1000px;
    margin: 50px auto;
    padding: 20px;
    background-color: #f9f9f9;
    border-radius: 10px;
    box-shadow: 0 4px 10px rgba(0, 0, 0, 0.1);
  }
  
  h2 {
    text-align: center;
    color: #333;
    margin-bottom: 20px;
  }
  
  label {
    margin-top: 20px;
    color: #555;
    font-weight: bold;
  }
  
  .form-input, .form-select, .form-textarea {
    padding: 10px;
    margin-top: 8px;
    border-radius: 5px;
    border: 1px solid #ddd;
    box-shadow: 0 2px 5px rgba(0, 0, 0, 0.05);
    font-size: 16px;
    transition: border-color 0.3s ease;
  }
  
  .form-input:focus, .form-select:focus, .form-textarea:focus {
    border-color: #4caf50;
    outline: none;
  }
  
  .form-textarea {
    height: 100px;
    resize: vertical;
  }
  
  .form-switch {
    display: flex;
    align-items: center;
    margin-top: 8px;
  }
  
  .form-switch input {
    margin-right: 10px;
  }
  
  .submit-button {
    margin-top: 30px;
    padding: 12px 20px;
    background-color: #4caf50;
    color: white;
    border: none;
    border-radius: 5px;
    font-size: 18px;
    cursor: pointer;
    transition: background-color 0.3s ease;
  }
  
  .submit-button:hover {
    background-color: #45a049;
  }
  
  .submit-button:active {
    background-color: #3e8e41;
  }
  </style>
  