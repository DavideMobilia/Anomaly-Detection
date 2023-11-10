La cartella Industry Lab-Project è suddivisa in 

Data
	Original- contenente i dati originali di FCA
	Processed- contente i dati processati da quelli originali o derivati
	Reference- dati rappresentanti le curve medie e bande di controllo
Models- contente i modelli di ML salvati
Script- 
	Part0- Data Extraction.ipynb
		estrazione dei dati utili dai file json originali
		input: dati original output:full_rows_df.pkl

	Part1- Data Preparation.ipynb
		filtraggio dai dati non utili o anomali e estrazione di un osservazione da utilizzare come test nel deploy
		input: full_rows_df.pkl  output:clean_rows_df.pkl
						test_value.pkl

	Part2- Statistical Anomaly Detection.ipynb
		sviluppo dell'algoritmo statistico
		input:clean_rows_df.pkl	output:	reference_volt_lag_curves.pkl
						reference_volt_curves.pkl
						reference_current_curves.pkl
						with_stat_anomalies.pkl

	Part3.a- Machine Learning_voltage.ipynb
		processing e svilupppo parte ML (voltage)
		input:clean_rows_df.pkl output: ML_voltage_with_anomalies.pkl
						iForest_volt.pkl

	Part3.b- Machine Learning_current.ipynb
		processing e svilupppo parte ML current
		input:clean_rows_df.pkl	output: ML_current_with_anomalies.pkl
						iForest_curr.pkl
	Part4- Anomaly Analysis.ipynb
		input: 	reference_volt_curves.pkl
			reference_current_curves.pkl
			with_stat_anomalies.pkl
			ML_voltage_with_anomalies
			ML_current_with_anomalies

	Part5- Deploy.ipynb
		input:	iForest_volt.pkl
			iForest_curr.pkl