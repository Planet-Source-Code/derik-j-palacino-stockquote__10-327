<div align="center">

## StockQuote


</div>

### Description

Retrieves the stock prices for the specified ticker symbol. Information retrieved can be modified by adjusting the parameters passed to the server.
 
### More Info
 
Stock Ticker symbol.

This uses the Yahoo! stock prices URL.

Stock prices


<span>             |<span>
---                |---
**Submitted On**   |
**By**             |[Derik J\. Palacino](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByAuthor/derik-j-palacino.md)
**Level**          |Beginner
**User Rating**    |5.0 (10 globes from 2 users)
**Compatibility**  |C\#
**Category**       |[Complete Applications](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByCategory/complete-applications__10-7.md)
**World**          |[\.Net \(C\#, VB\.net\)](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByWorld/net-c-vb-net.md)
**Archive File**   |[](https://github.com/Planet-Source-Code/derik-j-palacino-stockquote__10-327/archive/master.zip)





### Source Code

using System;
using System.Drawing;
using System.Collections;
using System.ComponentModel;
using System.Windows.Forms;
using System.Data;
namespace StockQuoter
{
	/// <summary>
	/// Summary description for Form1.
	/// </summary>
	public class Stocks : System.Windows.Forms.Form
	{
		private System.Windows.Forms.TextBox txtSymbol;
		private System.Windows.Forms.Button cmdGetQuotes;
		private System.Windows.Forms.Label lblTickerSymbol;
		private System.Windows.Forms.Label lblSymbol;
		private System.Windows.Forms.Label label2;
		private System.Windows.Forms.Label label4;
		private System.Windows.Forms.Label label6;
		private System.Windows.Forms.Button cmdExit;
		private System.Windows.Forms.Label lblLastTrade;
		private System.Windows.Forms.Label lblChange;
		private System.Windows.Forms.Label lblVolume;
		private Quoter qtStocks = new Quoter();
		/// <summary>
		/// Required designer variable.
		/// </summary>
		private System.ComponentModel.Container components = null;
		public Stocks()
		{
			InitializeComponent();
		}
		/// <summary>
		/// Clean up any resources being used.
		/// </summary>
		protected override void Dispose( bool disposing )
		{
			if( disposing )
			{
				if (components != null)
				{
					components.Dispose();
				}
			}
			base.Dispose( disposing );
		}
		#region Windows Form Designer generated code
		/// <summary>
		/// Required method for Designer support - do not modify
		/// the contents of this method with the code editor.
		/// </summary>
		private void InitializeComponent()
		{
			this.txtSymbol = new System.Windows.Forms.TextBox();
			this.cmdGetQuotes = new System.Windows.Forms.Button();
			this.lblTickerSymbol = new System.Windows.Forms.Label();
			this.lblSymbol = new System.Windows.Forms.Label();
			this.lblLastTrade = new System.Windows.Forms.Label();
			this.label2 = new System.Windows.Forms.Label();
			this.lblChange = new System.Windows.Forms.Label();
			this.label4 = new System.Windows.Forms.Label();
			this.lblVolume = new System.Windows.Forms.Label();
			this.label6 = new System.Windows.Forms.Label();
			this.cmdExit = new System.Windows.Forms.Button();
			this.SuspendLayout();
			//
			// txtSymbol
			//
			this.txtSymbol.Location = new System.Drawing.Point(32, 16);
			this.txtSymbol.Name = "txtSymbol";
			this.txtSymbol.TabIndex = 0;
			this.txtSymbol.Text = "";
			//
			// cmdGetQuotes
			//
			this.cmdGetQuotes.Location = new System.Drawing.Point(144, 15);
			this.cmdGetQuotes.Name = "cmdGetQuotes";
			this.cmdGetQuotes.TabIndex = 1;
			this.cmdGetQuotes.Text = "Get Quotes";
			this.cmdGetQuotes.Click += new System.EventHandler(this.cmdGetQuotes_Click);
			//
			// lblTickerSymbol
			//
			this.lblTickerSymbol.AutoSize = true;
			this.lblTickerSymbol.Location = new System.Drawing.Point(8, 56);
			this.lblTickerSymbol.Name = "lblTickerSymbol";
			this.lblTickerSymbol.Size = new System.Drawing.Size(76, 13);
			this.lblTickerSymbol.TabIndex = 2;
			this.lblTickerSymbol.Text = "Ticker Symbol";
			//
			// lblSymbol
			//
			this.lblSymbol.BorderStyle = System.Windows.Forms.BorderStyle.Fixed3D;
			this.lblSymbol.Location = new System.Drawing.Point(16, 72);
			this.lblSymbol.Name = "lblSymbol";
			this.lblSymbol.TabIndex = 3;
			//
			// lblLastTrade
			//
			this.lblLastTrade.BorderStyle = System.Windows.Forms.BorderStyle.Fixed3D;
			this.lblLastTrade.Location = new System.Drawing.Point(136, 72);
			this.lblLastTrade.Name = "lblLastTrade";
			this.lblLastTrade.TabIndex = 5;
			//
			// label2
			//
			this.label2.AutoSize = true;
			this.label2.Location = new System.Drawing.Point(128, 56);
			this.label2.Name = "label2";
			this.label2.Size = new System.Drawing.Size(58, 13);
			this.label2.TabIndex = 4;
			this.label2.Text = "Last Trade";
			//
			// lblChange
			//
			this.lblChange.BorderStyle = System.Windows.Forms.BorderStyle.Fixed3D;
			this.lblChange.Location = new System.Drawing.Point(16, 128);
			this.lblChange.Name = "lblChange";
			this.lblChange.TabIndex = 7;
			//
			// label4
			//
			this.label4.AutoSize = true;
			this.label4.Location = new System.Drawing.Point(8, 112);
			this.label4.Name = "label4";
			this.label4.Size = new System.Drawing.Size(44, 13);
			this.label4.TabIndex = 6;
			this.label4.Text = "Change";
			//
			// lblVolume
			//
			this.lblVolume.BorderStyle = System.Windows.Forms.BorderStyle.Fixed3D;
			this.lblVolume.Location = new System.Drawing.Point(136, 128);
			this.lblVolume.Name = "lblVolume";
			this.lblVolume.TabIndex = 9;
			//
			// label6
			//
			this.label6.AutoSize = true;
			this.label6.Location = new System.Drawing.Point(128, 112);
			this.label6.Name = "label6";
			this.label6.Size = new System.Drawing.Size(43, 13);
			this.label6.TabIndex = 8;
			this.label6.Text = "Volume";
			//
			// cmdExit
			//
			this.cmdExit.DialogResult = System.Windows.Forms.DialogResult.Cancel;
			this.cmdExit.Location = new System.Drawing.Point(16, 160);
			this.cmdExit.Name = "cmdExit";
			this.cmdExit.Size = new System.Drawing.Size(216, 23);
			this.cmdExit.TabIndex = 10;
			this.cmdExit.Text = "E x i t";
			this.cmdExit.Click += new System.EventHandler(this.cmdExit_Click);
			//
			// Stocks
			//
			this.AcceptButton = this.cmdGetQuotes;
			this.AutoScaleBaseSize = new System.Drawing.Size(5, 13);
			this.CancelButton = this.cmdExit;
			this.ClientSize = new System.Drawing.Size(248, 189);
			this.ControlBox = false;
			this.Controls.AddRange(new System.Windows.Forms.Control[] {
																		 this.cmdExit,
																		 this.lblVolume,
																		 this.label6,
																		 this.lblChange,
																		 this.label4,
																		 this.lblLastTrade,
																		 this.label2,
																		 this.lblSymbol,
																		 this.lblTickerSymbol,
																		 this.cmdGetQuotes,
																		 this.txtSymbol});
			this.Name = "Stocks";
			this.StartPosition = System.Windows.Forms.FormStartPosition.CenterScreen;
			this.Text = "Stock Quoter";
			this.ResumeLayout(false);
		}
		#endregion
		/// <summary>
		/// The main entry point for the application.
		/// </summary>
		[STAThread]
		static void Main()
		{
			Application.Run(new Stocks());
		}
		private void cmdExit_Click(object sender, System.EventArgs e)
		{
			Application.Exit();
		}
		private void cmdGetQuotes_Click(object sender, System.EventArgs e)
		{
			Quote objQuote = qtStocks.GetQuote(txtSymbol.Text);
			lblSymbol.Text = objQuote.Symbol;
			lblLastTrade.Text = objQuote.Last;
			lblChange.Text = objQuote.Change;
			lblVolume.Text = objQuote.Volume;
			this.Text = "Stock Quoter - " + objQuote.Name;
		}
	}
}
/**********************************************
*          Quoter.cs
***********************************************/
using System;
using System.IO;
using System.Net;
using System.Text;
public class Quoter
{
	public Quote GetQuote(string symbol)
	{
		string[] tokens;
		Quote q = new Quote();
		q.Symbol = symbol;
		try
		{
			HttpWebRequest wr = (HttpWebRequest)WebRequest.Create
				("http://quote.yahoo.com/d/quotes.csv?s="+ symbol + "&f=sl1d1t1c1ohgvj1pp2owern&e=.csv");
			HttpWebResponse ws = (HttpWebResponse)wr.GetResponse();
			StreamReader sr = new StreamReader(ws.GetResponseStream(),Encoding.ASCII);
			string data = sr.ReadLine();
			tokens = data.Split(new char[]{','});
			q.Symbol = tokens[0].Trim(new char[]{'"'});
			q.Last = tokens[1].Trim(new char[]{'"'});
			q.Change = tokens[11].Trim(new char[]{'"'});
			q.Name = tokens[16].Trim(new char[]{'"'});
			q.Volume = tokens[9].Trim(new char[]{'"'});
			return q;
		}
		catch(Exception e)
		{
			Console.WriteLine(e.ToString());
			Console.ReadLine();
			return q;
		}
	}
}
public class Quote
{
	string name;
	string symbol;
	string last;
	string change;
	string volume;
	public override string ToString()
	{
		return name + "\r\n" + symbol + "\r\n" + last + "\r\n" + change + "\r\n";
	}
	public string Last
	{
		get {return last;}
		set {last = value;}
	}
	public string Change
	{
		get {return change;}
		set {change = value;}
	}
	public string Symbol
	{
		get {return symbol;}
		set {symbol = value;}
	}
	public string Name
	{
		get {return name;}
		set {name = value;}
	}
	public string Volume
	{
		get {return volume;}
		set {volume = value;}
	}
}

