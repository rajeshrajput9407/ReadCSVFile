# ReadCSVFile

"private void button3_Click(object sender,EventArgs e)
		{
			List<Data> dataList =new List<Data>();
			OpenFileDialog file = new OpenFileDialog();
			file.Filter = "CSV Files (.CSV)|*.CSV";
			if(file.ShowDialog() == System.Windows.Forms.DialogResult.OK) {
				string filePath = file.FileName;
				string fileExt = Path.GetExtension(filePath);

				using(var reader = new StreamReader(filePath)) {
					while(!reader.EndOfStream) {
						Data data =new Data();
						var line = reader.ReadLine();
						var values = line.Split(',');
						
						data.slug  = "";
						data.name  = values[0];
						data.banner_link  = "";
						data.desc  = values[1];
						data.image  = values[2];
						dataList.Add(data);
					}
				}
				var s  = JsonConvert.SerializeObject(dataList);
			}
		}
		"
