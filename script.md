# Avalia-o
using System;
using System.Collections.Generic;
using System.ComponentModel;
using System.Data;
using System.Drawing;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
using System.Windows.Forms;

namespace ProjetoFinal
{
    public partial class FPrincipal : Form
    {
        public FPrincipal()
        {
            InitializeComponent();
        }

        private void button1_Click(object sender, EventArgs e)
        {
            FCadStatus fCadStatus = new FCadStatus();
            fCadStatus.ShowDialog();
        }

        private void button2_Click(object sender, EventArgs e)
        {
            FCadTarefa fcadtarefa = new FCadTarefa();
            fcadtarefa.ShowDialog();
        }

        private void button3_Click(object sender, EventArgs e)
        {
            FCadResp fcadresp = new FCadResp();
            fcadresp.ShowDialog();
        }

        private void tarefaBindingNavigatorSaveItem_Click(object sender, EventArgs e)
        {
            this.Validate();
            this.tarefaBindingSource.EndEdit();
            this.tableAdapterManager.UpdateAll(this.gtarefasDataSet);

        }

        private void FPrincipal_Load(object sender, EventArgs e)
        {
            // TODO: esta linha de código carrega dados na tabela 'gtarefasDataSet.Tarefa'. Você pode movê-la ou removê-la conforme necessário.
            this.tarefaTableAdapter.Fill(this.gtarefasDataSet.Tarefa);

        }
    }
}
