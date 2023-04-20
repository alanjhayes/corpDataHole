# CorpDataHole

CorpDataHole is an example application that uses the Windivert library to intercept and modify network packets on Windows operating systems. The application demonstrates how to use the Windivert library in C# to receive packets from a network interface, extract the text payload from the packets, classify the text using an Azure ML model, and drop the packet if it is classified as corporate data.

## Getting Started

To get started with CorpDataHole, follow these steps:

1. Clone or download the source code from the repository.
2. Open the solution file (`CorpDataHole.sln`) in Visual Studio.
3. Build the solution to generate the executable file (`CorpDataHole.exe`).
4. Run the executable file as an administrator.

## Usage

Once CorpDataHole is running, it will intercept and modify network packets according to the following rules:

1. Extract the text payload from the packet.
2. Classify the text using an Azure ML model.
3. Drop the packet if it is classified as corporate data.
4. Forward the packet if it is not classified as corporate data.

The example uses the following settings:

- Windivert filter: "ip" (captures only IP packets)
- Azure ML model: a binary classification model that predicts whether the text payload of a packet contains corporate data or not

You can modify the filter and the Azure ML model to suit your needs.

## Configuration

To configure CorpDataHole, edit the following variables in the `Program.cs` file:

- `AzureML.APIKey`: Your Azure ML API key.
- `InvokeRequestResponseService`: The endpoint URI of your Azure ML model.

## Requirements

To build and run CorpDataHole, you need the following:

- Windows operating system (Windows 7 or later)
- Visual Studio (2017 or later) with the .NET desktop development workload installed
- Windivert library (download from [here](https://www.reqrypt.org/windivert.html))
- Azure ML model (create a new model in the Azure Machine Learning Studio and publish it as a web service)

## License

CorpDataHole is licensed under the MIT License. See the `LICENSE` file for details.

## Acknowledgments

CorpDataHole is based on the Windivert library by Basil A. Abbas and the Azure ML service by Microsoft.
