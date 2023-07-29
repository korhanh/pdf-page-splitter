# SharePoint PDF Page Splitter with Python and Power Automate


This project aims to provide a solution for splitting PDF pages that are uploaded to SharePoint using Microsoft Power Automate. It leverages a Python web application hosted on an Ubuntu server to handle the PDF splitting process. The main goal is to divide the uploaded PDF into individual pages, save the split pages, and then store them back in SharePoint.

## How It Works

1. A PDF file is uploaded to SharePoint, triggering a Microsoft Power Automate flow.
2. The Power Automate flow sends an HTTP Request containing the uploaded PDF file to the Python web application hosted on the Ubuntu server.
3. The Python web application receives the PDF file, splits it into individual pages, and stores them in a specific output folder.
4. The Power Automate flow retrieves the split PDF pages from the Python web application and adds them back to SharePoint.
5. Optionally, the Power Automate flow can send a request to the Python web application to delete the temporary files from the Ubuntu server after they are successfully uploaded to SharePoint.

## Features

- Automatic PDF page splitting using Python and PyPDF2 library.
- Secure file transfer with HTTPS for communication between Power Automate and Python web application.
- Efficient handling of large PDF files with minimal memory usage.
- Automatic cleanup of temporary files from the Ubuntu server after uploading to SharePoint (optional).

## Requirements

- Python 3.x
- FastAPI (Python Web Framework)
- PyPDF2 (Python library for working with PDFs)
- Microsoft Power Automate subscription
- SharePoint account

## Getting Started

1. Clone this GitHub repository to your Ubuntu server.
2. Install the required Python libraries using `pip install -r requirements.txt`.
3. Run the Python web application using `uvicorn main:app --host 0.0.0.0 --port 8000`.
4. Create a Microsoft Power Automate flow triggered when a PDF file is uploaded to SharePoint.
5. Use the HTTP action in Power Automate to send a POST request with the PDF file as the payload to your Python web application's endpoint (`http://your-ubuntu-server-ip:8000/upload`).
6. Set up subsequent actions in the Power Automate flow to handle the returned split PDF files and add them back to SharePoint.
7. Optionally, add another HTTP action to send a DELETE request to the Python web application's endpoint (`http://your-ubuntu-server-ip:8000/delete/{file_name}`) to clean up temporary files.

## Contributions and Bug Reports

Contributions to this project are more than welcome! If you find any issues or have suggestions for improvements, please open an issue in this GitHub repository.

## License

This project is licensed under the [MIT License](https://github.com/korhanh/pdf-page-splitter/blob/main/LICENSE).

Feel free to use, modify, and distribute this project according to the terms specified in the license.

## Credits

This project is created and maintained by [korhanh]([link_to_your_github_profile](https://github.com/korhanh)).

If you use this project or find it helpful, consider giving it a star on GitHub!

Happy PDF page splitting! :rocket:
