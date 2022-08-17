package com.olivenbaum.digitodosdocumentos;

import android.app.Activity;
import android.os.Bundle;
import android.text.Editable;
import android.text.TextWatcher;
import android.util.SparseBooleanArray;
import android.view.View;
import android.widget.Button;
import android.widget.EditText;
import android.widget.ImageView;
import android.widget.LinearLayout;
import android.widget.ListView;
import android.widget.TextView;
import android.widget.Toast;

import java.util.ArrayList;
import java.util.Random;
import java.util.Timer;
import java.util.TimerTask;

public class CpfPageActivity extends Activity {

	private LinearLayout linear1;
	private LinearLayout linear2;
	private LinearLayout linear3;
	private LinearLayout linear4;
	private EditText numerocpf;
	private TextView textview1;
	private EditText digito;
	private ImageView imageview1;
	private ImageView imageview2;
	private TextView status;
	private Button gerar;
	private Button verificar;
	private Button limpar;

	private String cpf = "";
	private String name = "CPF";
	private String status_gerar = "";
	private double cont = 0;
	private int MAX_LENGTH = 9;
	private double somatorio_01 = 0;
	private double multiplicador = 0;
	private String digito_gerado = "";


	private Timer _timer = new Timer();
	private TimerTask time;


	@Override
	protected void onCreate(Bundle savedInstanceState) {
		super.onCreate(savedInstanceState);
		setContentView(R.layout.cpf_page);

		initialize();
		initializeLogic();
	}

	private void  initialize() {
		linear1 = (LinearLayout) findViewById(R.id.linear1);
		linear2 = (LinearLayout) findViewById(R.id.linear2);
		linear3 = (LinearLayout) findViewById(R.id.linear3);
		linear4 = (LinearLayout) findViewById(R.id.linear4);
		numerocpf = (EditText) findViewById(R.id.numerocpf);
		textview1 = (TextView) findViewById(R.id.textview1);
		digito = (EditText) findViewById(R.id.digito);
		imageview1 = (ImageView) findViewById(R.id.imageview1);
		imageview2 = (ImageView) findViewById(R.id.imageview2);
		status = (TextView) findViewById(R.id.status);
		gerar = (Button) findViewById(R.id.gerar);
		verificar = (Button) findViewById(R.id.verificar);
		limpar = (Button) findViewById(R.id.limpar);

		numerocpf.addTextChangedListener(new TextWatcher() {
			@Override
			public void beforeTextChanged(CharSequence s, int start, int count, int after) {
			}

			@Override
			public void onTextChanged(CharSequence s, int start, int before, int count) {
				if (s.length() == MAX_LENGTH) {
					digito.requestFocus(View.FOCUS_DOWN);
				}
			}

			@Override
			public void afterTextChanged(Editable s) {
			}
		});



		gerar.setOnClickListener(new View.OnClickListener() {
			@Override
			public void onClick(View _v) { 
				status.setVisibility(View.INVISIBLE);
				imageview1.setVisibility(View.GONE);
				imageview2.setVisibility(View.GONE);
				cont = 0;
				cpf = numerocpf.getText().toString();
				multiplicador = 10;
				somatorio_01 = 0;
				if (!(cpf.length() == 9)) {
					status.setText("Digite 9 números");
					status.setVisibility(View.VISIBLE);
					imageview2.setVisibility(View.VISIBLE);
					numerocpf.setTextColor(0xFFF44336);
					time = new TimerTask() {
								@Override
									public void run() {
										runOnUiThread(new Runnable() {
										@Override
											public void run() {
																numerocpf.setTextColor(0xFF000000);
											}
										});
									}
								};
								_timer.schedule(time, (int)(2000));
				}
				else {
					for(int _repeat10 = 0; _repeat10 < (int)(cpf.length()); _repeat10++) {
						somatorio_01 = somatorio_01 + (multiplicador * Double.parseDouble(cpf.substring((int)(cont), (int)(cont + 1))));
						cont++;
						multiplicador--;
					}
					if ((somatorio_01 % 11) < 2) {
						digito_gerado = "0";
					}
					else {
						digito_gerado = String.valueOf((long)(11 - (somatorio_01 % 11)));
					}
					cont = 0;
					multiplicador = 11;
					somatorio_01 = 0;
					for(int _repeat50 = 0; _repeat50 < (int)(cpf.length()); _repeat50++) {
						somatorio_01 = somatorio_01 + (multiplicador * Double.parseDouble(cpf.substring((int)(cont), (int)(cont + 1))));
						cont++;
						multiplicador--;
					}
					somatorio_01 = somatorio_01 + (Double.parseDouble(digito_gerado) * 2);
					if ((somatorio_01 % 11) < 2) {
						digito_gerado = digito_gerado.concat(String.valueOf((long)(0)));
					}
					else {
						digito_gerado = digito_gerado.concat(String.valueOf((long)(11 - (somatorio_01 % 11))));
					}
					digito.setText(digito_gerado);
					status_gerar = "CPF:  ";
					status_gerar = status_gerar.concat(cpf.substring((int)(0), (int)(3)));
					status_gerar = status_gerar.concat(".");
					status_gerar = status_gerar.concat(cpf.substring((int)(3), (int)(6)));
					status_gerar = status_gerar.concat(".");
					status_gerar = status_gerar.concat(cpf.substring((int)(6), (int)(9)));
					status_gerar = status_gerar.concat(" - ");
					status_gerar = status_gerar.concat(digito.getText().toString());
					status.setText(status_gerar);
					status.setVisibility(View.VISIBLE);
				}
			}
		});
		verificar.setOnClickListener(new View.OnClickListener() {
			@Override
			public void onClick(View _v) { 
				imageview1.setVisibility(View.GONE);
				imageview2.setVisibility(View.GONE);
				status.setVisibility(View.INVISIBLE);
				cont = 0;
				cpf = numerocpf.getText().toString();
				multiplicador = 10;
				somatorio_01 = 0;
				if (!(cpf.length() == 9)) {
					status.setText("Digite 9 números");
					status.setVisibility(View.VISIBLE);
					imageview2.setVisibility(View.VISIBLE);
					numerocpf.setTextColor(0xFFF44336);
					time = new TimerTask() {
								@Override
									public void run() {
										runOnUiThread(new Runnable() {
										@Override
											public void run() {
																numerocpf.setTextColor(0xFF000000);
											}
										});
									}
								};
								_timer.schedule(time, (int)(2000));
				}
				else {
					for(int _repeat18 = 0; _repeat18 < (int)(cpf.length()); _repeat18++) {
						somatorio_01 = somatorio_01 + (multiplicador * Double.parseDouble(cpf.substring((int)(cont), (int)(cont + 1))));
						cont++;
						multiplicador--;
					}
					if ((somatorio_01 % 11) < 2) {
						digito_gerado = "0";
					}
					else {
						digito_gerado = String.valueOf((long)(11 - (somatorio_01 % 11)));
					}
					cont = 0;
					multiplicador = 11;
					somatorio_01 = 0;
					for(int _repeat47 = 0; _repeat47 < (int)(cpf.length()); _repeat47++) {
						somatorio_01 = somatorio_01 + (multiplicador * Double.parseDouble(cpf.substring((int)(cont), (int)(cont + 1))));
						cont++;
						multiplicador--;
					}
					somatorio_01 = somatorio_01 + (Double.parseDouble(digito_gerado) * 2);
					if ((somatorio_01 % 11) < 2) {
						digito_gerado = digito_gerado.concat(String.valueOf((long)(0)));
					}
					else {
						digito_gerado = digito_gerado.concat(String.valueOf((long)(11 - (somatorio_01 % 11))));
					}
					if (digito.getText().toString().equals(digito_gerado)) {
						status.setText("CPF válido");
						imageview1.setVisibility(View.VISIBLE);
						status.setVisibility(View.VISIBLE);
					}
					else {
						status.setText("CPF inválido");
						imageview2.setVisibility(View.VISIBLE);
						status.setVisibility(View.VISIBLE);
					}
				}
			}
		});
		limpar.setOnClickListener(new View.OnClickListener() {
			@Override
			public void onClick(View _v) { 
				numerocpf.setText("");
				digito.setText("");
				imageview1.setVisibility(View.GONE);
				imageview2.setVisibility(View.GONE);
				status.setVisibility(View.INVISIBLE);
			}
		});

	}

	private void  initializeLogic() {
		setTitle("CPF");
		imageview1.setVisibility(View.GONE);
		imageview2.setVisibility(View.GONE);
		status.setVisibility(View.INVISIBLE);
	}




	// created automatically
	private void showMessage(String _s) {
		Toast.makeText(getApplicationContext(), _s, Toast.LENGTH_SHORT).show();
	}

	private int getRandom(int _minValue ,int _maxValue){
		Random random = new Random();
		return random.nextInt(_maxValue - _minValue + 1) + _minValue;
	}

	public ArrayList<Double> getCheckedItemPositionsToArray(ListView _list) {
		ArrayList<Double> _result = new ArrayList<Double>();
		SparseBooleanArray _arr = _list.getCheckedItemPositions();
		for (int _iIdx = 0; _iIdx < _arr.size(); _iIdx++) {
			if (_arr.valueAt(_iIdx))
				_result.add((double)_arr.keyAt(_iIdx));
		}
		return _result;
	}

}
