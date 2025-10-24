<!-- CALENDÁRIO -->
<div id="calendar-container" style="max-width:350px;margin:2rem auto;font-family:'Segoe UI',sans-serif;">
  <div id="calendar-header" style="display:flex;justify-content:space-between;align-items:center;margin-bottom:0.5rem;">
    <button id="prev-month" style="padding:0.3rem 0.6rem;border-radius:6px;border:none;background:#4B0082;color:white;cursor:pointer;">◀</button>
    <h3 id="month-year" style="margin:0;font-weight:bold;"></h3>
    <button id="next-month" style="padding:0.3rem 0.6rem;border-radius:6px;border:none;background:#4B0082;color:white;cursor:pointer;">▶</button>
  </div>
  <table id="calendar" style="width:100%;border-collapse:collapse;text-align:center;">
    <thead>
      <tr>
        <th>Dom</th>
        <th>Seg</th>
        <th>Ter</th>
        <th>Qua</th>
        <th>Qui</th>
        <th>Sex</th>
        <th>Sáb</th>
      </tr>
    </thead>
    <tbody id="calendar-body">
      <!-- Dias serão gerados aqui -->
    </tbody>
  </table>
</div>

<script>
// === CALENDÁRIO ===
const calMonthYear = document.getElementById('month-year');
const calBody = document.getElementById('calendar-body');
let todayCal = new Date();
let currentMonthCal = todayCal.getMonth();
let currentYearCal = todayCal.getFullYear();

function renderCalendar(month, year){
  const firstDay = new Date(year, month, 1).getDay();
  const daysInMonth = new Date(year, month + 1, 0).getDate();
  const months = ['Janeiro','Fevereiro','Março','Abril','Maio','Junho','Julho','Agosto','Setembro','Outubro','Novembro','Dezembro'];
  calMonthYear.textContent = months[month] + ' ' + year;

  calBody.innerHTML = '';
  let date = 1;
  for(let i=0;i<6;i++){
    let row = document.createElement('tr');
    for(let j=0;j<7;j++){
      let cell = document.createElement('td');
      cell.style.padding = '8px';
      cell.style.border = '1px solid rgba(255,215,0,0.2)';
      cell.style.borderRadius='6px';
      cell.style.transition='background 0.5s,color 0.5s';
      if(i===0 && j<firstDay){
        cell.textContent = '';
      } else if(date>daysInMonth){
        cell.textContent = '';
      } else {
        cell.textContent = date;
        // Dia atual destacado
        if(date===todayCal.getDate() && month===todayCal.getMonth() && year===todayCal.getFullYear()){
          cell.style.background = '#FFD700';
          cell.style.color = '#1a1a2e';
          cell.style.fontWeight='bold';
        }
        date++;
      }
      row.appendChild(cell);
    }
    calBody.appendChild(row);
  }

  // Ajusta cores para tema claro
  if(document.body.classList.contains('light')){
    Array.from(calBody.querySelectorAll('td')).forEach(td=>{
      td.style.border='1px solid #DAA520';
      td.style.color='#1a1a2e';
    });
  }else{
    Array.from(calBody.querySelectorAll('td')).forEach(td=>{
      td.style.border='1px solid rgba(255,215,0,0.2)';
      td.style.color='white';
    });
  }
}

document.getElementById('prev-month').addEventListener('click',()=>{
  currentMonthCal--;
  if(currentMonthCal<0){ currentMonthCal=11; currentYearCal--; }
  renderCalendar(currentMonthCal,currentYearCal);
});

document.getElementById('next-month').addEventListener('click',()=>{
  currentMonthCal++;
  if(currentMonthCal>11){ currentMonthCal=0; currentYearCal++; }
  renderCalendar(currentMonthCal,currentYearCal);
});

// Re-renderiza calendário ao trocar tema
const observerTheme = new MutationObserver(()=>renderCalendar(currentMonthCal,currentYearCal));
observerTheme.observe(document.body,{attributes:true,class:true});

// Inicializa
renderCalendar(currentMonthCal,currentYearCal);
</script>
