# FileUtil
	//static final String FILE_NAME = "D:\\Temp\\Programming_Challenges.pdf"; //huge GB file
	static final String FILE_NAME = "D:\\Temp\\pdf.pdf"; //small KB file

	public static void main(String[] args) {

			File file = new File(FILE_NAME);
			if (!file.exists() || !file.isFile()) return;

			System.out.println(getStringSizeLengthFile(file.length()));

	}

	public static String getStringSizeLengthFile(long size) {

	    DecimalFormat df = new DecimalFormat("0.00");

	    float sizeKb = 1024.0f;
	    float sizeMo = sizeKb * sizeKb;
	    float sizeGo = sizeMo * sizeKb;
	    float sizeTerra = sizeGo * sizeKb;


	    if(size < sizeMo)
	        return df.format(size / sizeKb)+ " KB";
	    else if(size < sizeGo)
	        return df.format(size / sizeMo) + " MB";
	    else if(size < sizeTerra)
	        return df.format(size / sizeGo) + " GB";

	    return "";
	}
