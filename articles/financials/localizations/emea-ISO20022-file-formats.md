<?xml version="1.0" encoding="UTF-8"?>
<xliff xmlns:logoport="urn:logoport:xliffeditor:xliff-extras:1.0" xmlns:tilt="urn:logoport:xliffeditor:tilt-non-translatables:1.0" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns="urn:oasis:names:tc:xliff:document:1.2" xmlns:xliffext="urn:microsoft:content:schema:xliffextensions" version="1.2" xsi:schemaLocation="urn:oasis:names:tc:xliff:document:1.2 xliff-core-1.2-transitional.xsd">
  <file datatype="xml" source-language="en-US" original="emea-ISO20022-file-formats.md" target-language="pl-PL">
    <header>
      <tool tool-company="Microsoft" tool-version="1.0-7889195" tool-name="mdxliff" tool-id="mdxliff"/>
      <xliffext:skl_file_name>emea-ISO20022-file-formats.35e138.d91e937c62d4d498e67d753e39676514835f4161.skl</xliffext:skl_file_name>
      <xliffext:version>1.2</xliffext:version>
      <xliffext:ms.openlocfilehash>d91e937c62d4d498e67d753e39676514835f4161</xliffext:ms.openlocfilehash>
      <xliffext:ms.sourcegitcommit>9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b</xliffext:ms.sourcegitcommit>
      <xliffext:ms.lasthandoff>05/15/2019</xliffext:ms.lasthandoff>
      <xliffext:ms.openlocfilepath>articles\financials\localizations\emea-ISO20022-file-formats.md</xliffext:ms.openlocfilepath>
    </header>
    <body>
      <group extype="content" id="content">
        <trans-unit xml:space="preserve" translate="yes" id="101" restype="x-metadata">
          <source>ISO20022 files import</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Importowanie plików ISO20022</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="102" restype="x-metadata">
          <source>This topic explains how to import payment files of the ISO 20022 camt.054 and pain.002 formats into Microsoft Dynamics 365 for Finance and Operations.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">W tym temacie wyjaśniono, jak importować pliki płatności w formatach ISO 20022 camt.054 i pain.002 w Microsoft Dynamics 365 for Finance and Operations.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="103">
          <source>Import ISO20022 files</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Importowanie plików ISO20022</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="104">
          <source>You can import payment files that have the following formats:</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Można importować pliki płatności mające następujące formaty:</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="105">
          <source><bpt id="p1">**</bpt>ISO20022 camt.054 credit advice<ept id="p1">**</ept> – Import incoming payments from a file in this format into the Customer payment journal.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm"><bpt id="p1">**</bpt>Zawiadomienie kredytowe ISO20022 camt.054<ept id="p1">**</ept> — importowanie płatności przychodzących z pliku w tym formacie do arkusza płatności odbiorców.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="106">
          <source><bpt id="p1">**</bpt>ISO20022 pain.002 status return<ept id="p1">**</ept> and <bpt id="p2">**</bpt>ISO20022 camt.054 debit advice<ept id="p2">**</ept> – Import return files in these formats into the AP Payment transfer journal.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm"><bpt id="p1">**</bpt>Informacja zwrotna o stanie ISO20022 pain.002<ept id="p1">**</ept> i <bpt id="p2">**</bpt>zawiadomienie debetowe ISO20022 camt.054<ept id="p2">**</ept> — importowanie plików zwrotnych w tych formatach do arkusza przelewów w module Rozrachunki z dostawcami.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="107">
          <source>Prerequisites for importing the camt.054 credit advice file</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Wymagania wstępne dotyczące importowania pliku zawiadomienia kredytowego camt.054</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="108">
          <source>You must complete the following prerequisites to import bank notification messages in the camt.054.001.002 format into the Customer payment journal.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Należy wykonać poniższe wymagania wstępne, aby importować komunikaty powiadomień bankowych w formacie camt.054.001.002 do arkusza płatności odbiorców.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="109">
          <source>Import the <bpt id="p1">**</bpt>ISO20022 camt.054<ept id="p1">**</ept> Electronic reporting (ER) configuration from Microsoft Dynamics Lifecycle Services (LCS).</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Zaimportuj konfigurację <bpt id="p1">**</bpt>ISO20022 camt.054<ept id="p1">**</ept> modułu Raportowanie elektroniczne (ER) z usługi Microsoft Dynamics Lifecycle Services (LCS).</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="110">
          <source>Then, on the <bpt id="p1">**</bpt>Customer method of payment<ept id="p1">**</ept> page, in the <bpt id="p2">**</bpt>Import format configuration<ept id="p2">**</ept> field, select that configuration.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Następnie na stronie <bpt id="p1">**</bpt>Metoda płatności odbiorcy<ept id="p1">**</ept> w polu <bpt id="p2">**</bpt>Konfiguracja formatu importu<ept id="p2">**</ept> zaznacz tę konfigurację.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="111">
          <source>For more information, see <bpt id="p1">[</bpt>File formats for methods of payment<ept id="p1">](emea-select-file-formats-for-the-method-of-payments.md)</ept>.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Aby uzyskać więcej informacji, zobacz <bpt id="p1">[</bpt>Formaty plików metod płatności<ept id="p1">](emea-select-file-formats-for-the-method-of-payments.md)</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="112">
          <source>On the <bpt id="p1">**</bpt>All customers<ept id="p1">**</ept> page, enter a name and organization number for each customer.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Na stronie <bpt id="p1">**</bpt>Wszyscy odbiorcy<ept id="p1">**</ept> wprowadź nazwę i numer organizacji dla każdego odbiorcy.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="113">
          <source>On the <bpt id="p1">**</bpt>Customer bank account<ept id="p1">**</ept> page, set up a customer bank account record by entering the following information: IBAN or bank account number, and SWIFT code or routing number.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Na stronie <bpt id="p1">**</bpt>Konto bankowe odbiorcy<ept id="p1">**</ept> skonfiguruj rekord konta bankowego odbiorcy przez wprowadzenie następujących informacji: numer IBAN lub numer konta bankowego oraz kod SWIFT lub kod banku.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="114">
          <source>On the <bpt id="p1">**</bpt>Bank accounts<ept id="p1">**</ept> page, set up legal entity bank accounts by entering the following information: IBAN or bank account number, SWIFT code or routing number, currency, and address.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Na stronie <bpt id="p1">**</bpt>Konta bankowe<ept id="p1">**</ept> skonfiguruj konta bankowe firmy przez wprowadzenie następujących informacji: numer IBAN lub numer konta bankowego, kod SWIFT lub kod banku, waluta i adres.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="115">
          <source>If you plan to use Advanced bank reconciliation, on the <bpt id="p1">**</bpt>Reconciliation<ept id="p1">**</ept> FastTab, set the <bpt id="p2">**</bpt>Advanced bank reconciliation<ept id="p2">**</ept> option to <bpt id="p3">**</bpt>Yes<ept id="p3">**</ept>.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Jeśli zamierzasz używać funkcji Zaawansowane uzgadnianie konta bankowego, na skróconej karcie <bpt id="p1">**</bpt>Uzgodnienie<ept id="p1">**</ept> w opcji <bpt id="p2">**</bpt>Zaawansowane uzgadnianie konta bankowego<ept id="p2">**</ept> ustaw wartość <bpt id="p3">**</bpt>Tak<ept id="p3">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="116">
          <source>If you plan to reconcile unposted imported payments, set the <bpt id="p1">**</bpt>Use bank statements as confirmation of electronic payments<ept id="p1">**</ept> option to <bpt id="p2">**</bpt>Yes<ept id="p2">**</ept>.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Jeśli zamierzasz uzgadniać niezaksięgowane importowane płatności, w opcji <bpt id="p1">**</bpt>Uznaj wyciągi bankowe jako potwierdzenia płatności elektronicznych<ept id="p1">**</ept> ustaw wartość <bpt id="p2">**</bpt>Tak<ept id="p2">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="117">
          <source>Optional: On the <bpt id="p1">**</bpt>Transaction code mapping<ept id="p1">**</ept> page, set up the mapping between bank transaction codes in the file and bank transaction types.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Opcjonalnie: Na stronie <bpt id="p1">**</bpt>Mapowanie kodu transakcji<ept id="p1">**</ept> skonfiguruj mapowanie między kodami transakcji bankowych w pliku a typami transakcji bankowych.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="118">
          <source>If the file contains transaction charges that you want to post together with the incoming payment, create a payment fee on the <bpt id="p1">**</bpt>Customer payment fee<ept id="p1">**</ept> page.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Jeżeli plik zawiera opłaty za transakcje, które chcesz zaksięgować razem z przychodzącą płatnością, otwórz opłatę od płatności na stronie <bpt id="p1">**</bpt>Opłata od płatności odbiorcy<ept id="p1">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="119">
          <source>Then, on the <bpt id="p1">**</bpt>Methods of payment<ept id="p1">**</ept> page, associate the payment fee with the bank account in the payment fee setup.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Następnie na stronie <bpt id="p1">**</bpt>Metody płatności<ept id="p1">**</ept> skojarz opłatę od płatności z kontem bankowym w ustawieniach opłat od płatności.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="120">
          <source>If ESR payments will be imported and will contain ISR references (applicable for legal entities in Switzerland), complete the following setup:</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Jeśli będą importowane płatności ESR zawierające odniesienia do dokumentów płatności ISR (dotyczy firm w Szwajcarii), należy wykonać następującą konfigurację:</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="121">
          <source>In the <bpt id="p1">**</bpt>Customer payments, account lengths<ept id="p1">**</ept> field, enter the length of the customer code that is used in ISR references or for automatic identification of the customer.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">W polu <bpt id="p1">**</bpt>Płatności odbiorcy, długość konta<ept id="p1">**</ept> wprowadź długość kodu odbiorcy, który będzie używany w odniesieniach do dokumentu płatności ISR lub do automatycznej identyfikacji odbiorcy.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="122">
          <source>Make sure that the customer number and invoice number (number sequences) contain only digits.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Upewnij się, że numer odbiorcy i numer faktury (numeracje) zawierają tylko cyfry.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="123">
          <source>They must contain no other characters.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Nie może w nich być żadnych innych znaków.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="124">
          <source>The invoice number must not have leading zeros.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Numer faktury nie może zawierać zer na początku.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="125">
          <source>Enter the ESR, BESR, and routing number for the legal entity bank account.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Wprowadź numery ESR i BESR oraz kod banku dla rachunku bankowego firmy.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="126">
          <source>For more information, see <bpt id="p1">[</bpt>legacy ESR feature<ept id="p1">](emea-che-esr-customer-payments-import.md)</ept>, because similar settings are required.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Aby uzyskać więcej informacji, zobacz <bpt id="p1">[</bpt>Starsza funkcja ESR<ept id="p1">](emea-che-esr-customer-payments-import.md)</ept>, ponieważ są wymagane podobne ustawienia.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="127">
          <source>Import the camt.054 credit advice file into the Customer payment journal</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Importowanie pliku zawiadomienia kredytowego camt.054 do arkusza płatności odbiorców</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="128">
          <source>On the <bpt id="p1">**</bpt>Customer payment journal lines<ept id="p1">**</ept> page, click <bpt id="p2">**</bpt>Functions<ept id="p2">**</ept><ph id="ph1"> &gt; </ph><bpt id="p3">**</bpt>Import payments<ept id="p3">**</ept>.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Na stronie <bpt id="p1">**</bpt>Wiersze arkusza płatności odbiorców<ept id="p1">**</ept> kliknij kolejno opcje <bpt id="p2">**</bpt>Funkcje<ept id="p2">**</ept><ph id="ph1"> &gt; </ph><bpt id="p3">**</bpt>Import płatności<ept id="p3">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="129">
          <source>Select the method of payment that has the required settings for the ISO20022 camt.054 format.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Wybierz metodę płatności, która ma wymagane ustawienia formatu camt.054 ISO20022.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="130">
          <source>Specify the required parameters and the path of the file, and then click <bpt id="p1">**</bpt>OK<ept id="p1">**</ept>.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Określ wymagane parametry i ścieżkę pliku, a następnie kliknij przycisk <bpt id="p1">**</bpt>OK<ept id="p1">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="131">
          <source>The file is imported.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Plik zostanie zaimportowany.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="132">
          <source>Prerequisites for importing files in the pain.002 status return and camt.054 debit advice formats into the AP Payment transfer journal</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Warunki wstępne importowania plików informacji zwrotnej o stanie w formacie ISO20022 pain.002 i zawiadomienia debetowego w formacie ISO20022 camt.054 do arkusza przelewów w module Rozrachunki z dostawcami</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="133">
          <source>You must complete the following prerequisites to import bank messages in the following ISO20022 formats to the <bpt id="p1">**</bpt>Vendor payment transfer<ept id="p1">**</ept> page: pain.002.001.003 status return messages and camt.054.001.002 debit advice.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Należy spełnić poniższe warunki wstępne, aby importować komunikaty bankowe w następujących formatach ISO20022 do strony <bpt id="p1">**</bpt>Przelew do dostawcy<ept id="p1">**</ept>: komunikaty zwrotne o stanie pain.002.001.003 i zawiadomienia debetowe camt.054.001.002.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="134">
          <source>Import the <bpt id="p1">**</bpt>ISO20022 camt.054<ept id="p1">**</ept> and <bpt id="p2">**</bpt>ISO20022 pain.002<ept id="p2">**</ept> ER configurations from LCS.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Zaimportuj konfiguracje ER <bpt id="p1">**</bpt>ISO20022 camt.054<ept id="p1">**</ept> i <bpt id="p2">**</bpt>ISO20022 pain.002<ept id="p2">**</ept> z usługi LCS.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="135">
          <source>On the <bpt id="p1">**</bpt>Vendor method of payment<ept id="p1">**</ept> page, in the <bpt id="p2">**</bpt>Return format configuration<ept id="p2">**</ept> and <bpt id="p3">**</bpt>Return format secondary configuration<ept id="p3">**</ept> fields, select the ER configurations that you imported.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Na stronie <bpt id="p1">**</bpt>Metoda płatności dostawcy<ept id="p1">**</ept> w polach <bpt id="p2">**</bpt>Konfiguracja formatu zwrotnego<ept id="p2">**</ept> i <bpt id="p3">**</bpt>Pomocnicza konfiguracja formatu zwrotnego<ept id="p3">**</ept> zaznacz zaimportowane konfiguracje modułu ER.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="136">
          <source>You will have to activate the generic electronic return format for the selected method of payment.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Trzeba będzie aktywować standardowy format elektroniczny informacji zwrotnych dla wybranej metody płatności.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="137">
          <source>On the <bpt id="p1">**</bpt>Return format status mapping<ept id="p1">**</ept> page, set up the mapping of status codes between pain.002 statuses and Vendor payment journal statuses.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Na stronie <bpt id="p1">**</bpt>Mapowanie stanu formatu zwrotnego<ept id="p1">**</ept> skonfiguruj mapowanie kodów stanu między stanami formatu pain.002 a stanami arkusza płatności dostawców.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="138">
          <source>Here is an example of a status setup.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Oto przykład konfiguracji stanów.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="139">
          <source>Return status</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Stan zwrotu</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="140">
          <source>Payment status</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Stan płatności</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="141">
          <source>RJCT</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">RJCT</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="142">
          <source>Rejected</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Odrzucona</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="143">
          <source>ACCP</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">ACCP</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="144">
          <source>Accepted</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Zaakceptowany</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="145">
          <source>ACSP</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">ACSP</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="146">
          <source>Received</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Odebrane</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="147">
          <source>On the <bpt id="p1">**</bpt>Return format error codes<ept id="p1">**</ept> page, set up pain.002 error codes and descriptions in accordance with external ISO20022 status reason codes.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Na stronie <bpt id="p1">**</bpt>Kody błędów formatu zwrotnego<ept id="p1">**</ept> skonfiguruj kody błędów i opisy formatu pain.002 kody zgodnie z zewnętrznymi kodami przyczyn stanu w standardzie ISO20022.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="148">
          <source>Here is an example of part of an error code setup.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Poniżej przedstawiono przykład częściowej konfiguracji kodów błędów.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="149">
          <source>Code</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Kod</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="150">
          <source>Name</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Nazwisko</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="151">
          <source>AC01</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">AC01</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="152">
          <source>IncorrectAccountNumber</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">IncorrectAccountNumber</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="153">
          <source>AC02</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">AC02</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="154">
          <source>InvalidDebtorAccountNumber</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">InvalidDebtorAccountNumber</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="155">
          <source>AC03</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">AC03</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="156">
          <source>InvalidCreditorAccountNumber</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">InvalidCreditorAccountNumber</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="157">
          <source>AC04</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">AC04</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="158">
          <source>ClosedAccountNumber</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">ClosedAccountNumber</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="159">
          <source>AC05</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">AC05</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="160">
          <source>ClosedDebtorAccountNumber</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">ClosedDebtorAccountNumber</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="161">
          <source>AC06</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">AC06</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="162">
          <source>BlockedAccount</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">BlockedAccount</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="163">
          <source>If the camt.054 file contains transaction charges that you want to post together with the incoming payment, create a payment fee on the <bpt id="p1">**</bpt>Vendor payment fee<ept id="p1">**</ept> page.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Jeżeli plik camt.054 zawiera opłaty za transakcje, które chcesz zaksięgować razem z przychodzącą płatnością, otwórz opłatę od płatności na stronie <bpt id="p1">**</bpt>Opłata od płatności dostawcy<ept id="p1">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="164">
          <source>Then, on the <bpt id="p1">**</bpt>Methods of payment<ept id="p1">**</ept> page, associate the payment fee with the bank account in the payment fee setup.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Następnie na stronie <bpt id="p1">**</bpt>Metody płatności<ept id="p1">**</ept> skojarz opłatę od płatności z kontem bankowym w ustawieniach opłat od płatności.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="165">
          <source>Import the pain.002 status return or camt.054 debit advice files into the Vendor payment journal</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Importowanie plików informacji zwrotnej o stanie pain.002 lub zawiadomienia debetowego camt.054 do arkusza płatności dostawców</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="166">
          <source>Open the <bpt id="p1">**</bpt>Payment transfers<ept id="p1">**</ept> page in Accounts Payable menu.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Otwórz stronę <bpt id="p1">**</bpt>Przelewy<ept id="p1">**</ept> stronę w menu modułu Rozrachunki z dostawcami.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="167">
          <source>On the <bpt id="p1">**</bpt>Payment transfers<ept id="p1">**</ept> page, click <bpt id="p2">**</bpt>Return file - vendor<ept id="p2">**</ept>.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Na stronie <bpt id="p1">**</bpt>Przelewy<ept id="p1">**</ept> kliknij opcję <bpt id="p2">**</bpt>Plik zwrotny — Dostawca<ept id="p2">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="168">
          <source>Select the method of payment that has the required settings for ISO20022 files, and then click <bpt id="p1">**</bpt>OK<ept id="p1">**</ept>.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Wybierz metodę płatności, która ma wymagane ustawienia plików formatu ISO20022, i kliknij przycisk <bpt id="p1">**</bpt>OK<ept id="p1">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="169">
          <source>Select the file format that you plan to import, and then click <bpt id="p1">**</bpt>OK<ept id="p1">**</ept>.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Zaznacz format pliku, który chcesz zaimportować, a następnie kliknij przycisk <bpt id="p1">**</bpt>OK<ept id="p1">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="170">
          <source>Specify the required parameters and the path of the file, and then click <bpt id="p1">**</bpt>OK<ept id="p1">**</ept>.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Określ wymagane parametry i ścieżkę pliku, a następnie kliknij przycisk <bpt id="p1">**</bpt>OK<ept id="p1">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="171">
          <source>If you're importing the pain.002 file, the status of vendor payment lines is updated, based the information in the imported file.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Jeśli importujesz plik pain.002, stan wierszy płatności do dostawców zostanie zaktualizowany zgodnie z informacjami w importowanym pliku.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="172">
          <source>If you're importing the camt.054 file, you should specify the following additional parameters:</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">W przypadku importowania pliku camt.054 należy określić następujące dodatkowe parametry:</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="173">
          <source><bpt id="p1">**</bpt>Fee ID<ept id="p1">**</ept> – Enter the Fee ID which will define new payment fee lines, which will be created on the Vendor payment journal line if a charge amount is present in the camt.054 file.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm"><bpt id="p1">**</bpt>Identyfikator opłaty<ept id="p1">**</ept> — wprowadź identyfikator opłaty, który będzie definiował nowe wiersze opłat od płatności tworzone w wierszu arkusza płatności dostawców w przypadku, gdy plik camt.054 zawiera kwotę opłaty.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="174">
          <source><bpt id="p1">**</bpt>New journal name<ept id="p1">**</ept> and <bpt id="p2">**</bpt>New journal description<ept id="p2">**</ept> – Enter the name and description of the journal that processed transactions will be transferred to.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm"><bpt id="p1">**</bpt>Nazwa nowego arkusza<ept id="p1">**</ept> i <bpt id="p2">**</bpt>Opis nowego arkusza<ept id="p2">**</ept> — wprowadź nazwę i opis arkusza, do którego będą przenoszone przetworzone transakcje.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="175">
          <source>After the transfer, new voucher numbers should be assigned in the new journal.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Po przeniesieniu w nowym arkuszu powinny zostać przypisane nowe numery załączników.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="176">
          <source><bpt id="p1">**</bpt>Import direct debit transactions<ept id="p1">**</ept> – Set this option to <bpt id="p2">**</bpt>Yes<ept id="p2">**</ept> if outgoing direct debits must be imported into the Vendor payment journal.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm"><bpt id="p1">**</bpt>Importuj transakcje poleceń zapłaty<ept id="p1">**</ept> — ustaw w tej opcji wartość <bpt id="p2">**</bpt>Tak<ept id="p2">**</ept>, jeśli wychodzące polecenia zapłaty muszą być importowane do arkusza płatności dostawców.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="177">
          <source><bpt id="p1">**</bpt>Journal name<ept id="p1">**</ept> – Define a new journal name for the imported direct debit transactions.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm"><bpt id="p1">**</bpt>Nazwa arkusza<ept id="p1">**</ept> — podaj nazwę nowego arkusza na importowane transakcje polecenia zapłaty.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="178">
          <source><bpt id="p1">**</bpt>Settle transactions<ept id="p1">**</ept> – Set this option to <bpt id="p2">**</bpt>Yes<ept id="p2">**</ept> if imported vendor payments must be settled with invoices that are found in the system.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm"><bpt id="p1">**</bpt>Rozlicz transakcje<ept id="p1">**</ept> — ustaw w tej opcji wartość <bpt id="p2">**</bpt>Tak<ept id="p2">**</ept>, jeśli importowane płatności do dostawców muszą być rozliczane względem faktur znajdujących się w systemie.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="179">
          <source>You can view the imported information on the <bpt id="p1">**</bpt>Payment transfers<ept id="p1">**</ept> page.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Zaimportowane informacje można przejrzeć na stronie <bpt id="p1">**</bpt>Przelewy<ept id="p1">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="180">
          <source>Additional details</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Dodatkowe szczegóły</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="181">
          <source>When you import a format configuration from LCS, you import the whole configuration tree which means that the Model and Model mapping configurations are included.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Podczas importowania konfiguracji formatu z usługi LCS importujesz całe drzewo konfiguracja, a więc również konfiguracje modelu i mapowania modelu.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="182">
          <source>In the Payment model starting from version 8, the mappings are located in separate ER configurations in the solution tree (Payment model mapping 1611, Payment model mapping to destination ISO20022, etc).</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">W modelu płatności począwszy od wersji 8 mapowania znajdują się w oddzielnych konfiguracjach raportowania elektronicznego w drzewie rozwiązania (Mapowanie modelu płatności 1611, Mapowanie modelu płatności do lokalizacji docelowej ISO20022 itp.).</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="183">
          <source>There are many different payment formats under one model (Payment model), thus separate mapping handling is a key for easy solution maintenance.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">W jednym modelu (modelu płatności) istnieje wiele różnych formatów płatności, dlatego oddzielna obsługa mapowań jest kluczowa dla łatwego zarządzania rozwiązaniem.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="184">
          <source>For example, consider this scenario: you use ISO20022 payments to generate credit transfer files and then you import the return messages from the bank.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Rozważmy na przykład następujący scenariusz: używasz płatności ISO20022 do generowania plików poleceń przelewu, a następnie importujesz komunikaty zwrotne z banku.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="185">
          <source>In this scenario, you should use the following configurations:</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">W tym scenariuszu należy korzystać z następujących konfiguracji:</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="186">
          <source><bpt id="p1">**</bpt>Payment model<ept id="p1">**</ept></source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm"><bpt id="p1">**</bpt>Model płatności<ept id="p1">**</ept></target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="187">
          <source><bpt id="p1">**</bpt>Payment model mapping 1611<ept id="p1">**</ept> – this mapping will be used to generate the export file</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm"><bpt id="p1">**</bpt>Mapowanie modelu płatności 1611<ept id="p1">**</ept> — to mapowanie będzie używane do generowania pliku eksportu</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="188">
          <source><bpt id="p1">**</bpt>Payment model mapping to destination ISO20022<ept id="p1">**</ept> – this configuration includes all mappings which will be used to import the data (“to destination” mapping direction)</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm"><bpt id="p1">**</bpt>Mapowanie modelu płatności do lokalizacji docelowej ISO20022<ept id="p1">**</ept> — ta konfiguracja zawiera wszystkie mapowania, które będą używane do importowania danych (kierunek mapowania „do lokalizacji docelowej”)</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="189">
          <source><bpt id="p1">**</bpt>ISO20022 Credit transfer<ept id="p1">**</ept> – this configuration includes a format component that is responsible for export file generation (pain.001) based on the Payment model mapping 1611, as well as a format to model mapping component which will be used together with Payment model mapping to destination ISO20022 to register exported payments in the system for further import purposes (import in CustVendProcessedPayments technical table)</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm"><bpt id="p1">**</bpt>Polecenie przelewu ISO20022<ept id="p1">**</ept> — ta konfiguracja zawiera składnik formatu odpowiedzialny za generowanie pliku eksportu (pain.001) na podstawie konfiguracji Mapowanie modelu płatności 1611, a także format do modelowania składnika mapowania, który będzie używany razem z konfiguracją Mapowanie modelu płatności do lokalizacji docelowej ISO20022 w celu rejestrowania wyeksportowanych płatności w systemie na potrzeby dalszego importu (import w tabeli technicznej CustVendProcessedPayments)</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="190">
          <source><bpt id="p1">**</bpt>ISO20022 Credit transfer (CE)<ept id="p1">**</ept>, where CE correspond to country extension – derived format to the ISO20022 Credit transfer with the same structure and with certain country-specific differences</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm"><bpt id="p1">**</bpt>Polecenie przelewu ISO20022 (CE)<ept id="p1">**</ept>, gdzie CE odpowiada rozszerzeniu kraju — format pochodny od formatu Polecenie przelewu ISO20022 z taką samą strukturą i pewnymi różnicami specyficznymi dla krajów</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="191">
          <source><bpt id="p1">**</bpt>Pain.002<ept id="p1">**</ept> – this format will be used together with the Payment model mapping to destination ISO20022 in order to import the pain.002 file into vendor payments transfers journal</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm"><bpt id="p1">**</bpt>Pain.002<ept id="p1">**</ept> — ten format zostanie użyty wraz z konfiguracją Mapowanie modelu płatności do lokalizacji docelowej ISO20022 w celu zaimportowania pliku pain.002 do arkusza przeniesień płatności dostawców</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="192">
          <source><bpt id="p1">**</bpt>Camt.054<ept id="p1">**</ept> – this format will be used together with the Payment model mapping to destination ISO20022 to import the camt.054 file into vendor payments transfers journal.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm"><bpt id="p1">**</bpt>Camt.054<ept id="p1">**</ept> — ten format zostanie użyty wraz z konfiguracją Mapowanie modelu płatności do lokalizacji docelowej ISO20022 w celu zaimportowania pliku camt.054 do arkusza przeniesień płatności dostawców</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="193">
          <source>The same format configuration will be used in customer payments import functionality, but the different mapping will be used in the Payment model mapping to destination ISO20022 configuration.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Ta sama konfiguracja formatu będzie używana w funkcji importowania płatności odbiorców, ale inne mapowanie będzie używane w konfiguracji Mapowanie modelu płatności do lokalizacji docelowej ISO20022.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="194">
          <source>For more information about Electronic reporting, refer to <bpt id="p1">[</bpt>Electronic reporting overview<ept id="p1">](../../dev-itpro/analytics/general-electronic-reporting.md)</ept>.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Aby uzyskać więcej informacji na temat raportowania elektronicznego, zobacz <bpt id="p1">[</bpt>Omówienie raportowania elektronicznego<ept id="p1">](../../dev-itpro/analytics/general-electronic-reporting.md)</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="195">
          <source>Additional resources</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Dodatkowe zasoby</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="196">
          <source><bpt id="p1">[</bpt>Create and export vendor payments using ISO20022 payment format<ept id="p1">](./tasks/create-export-vendor-payments-iso20022-payment-format.md)</ept></source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm"><bpt id="p1">[</bpt>Tworzenie i eksport płatności dla dostawcy przy użyciu formatu płatności ISO20022<ept id="p1">](./tasks/create-export-vendor-payments-iso20022-payment-format.md)</ept></target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="197">
          <source><bpt id="p1">[</bpt>Import ISO20022 credit transfer configuration<ept id="p1">](./tasks/import-iso20022-credit-transfer-configuration.md)</ept></source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm"><bpt id="p1">[</bpt>Importowanie konfiguracji polecenia przelewu ISO20022<ept id="p1">](./tasks/import-iso20022-credit-transfer-configuration.md)</ept></target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="198">
          <source><bpt id="p1">[</bpt>Import ISO20022 direct debit configuration<ept id="p1">](./tasks/import-iso20022-direct-debit-configuration.md)</ept></source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm"><bpt id="p1">[</bpt>Importowanie konfiguracji polecenia zapłaty ISO20022<ept id="p1">](./tasks/import-iso20022-direct-debit-configuration.md)</ept></target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="199">
          <source><bpt id="p1">[</bpt>Set up company bank accounts for ISO20022 credit transfers<ept id="p1">](./tasks/set-up-company-bank-accounts-iso20022-credit-transfers.md)</ept></source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm"><bpt id="p1">[</bpt>Konfigurowanie kont bankowych firmy dla poleceń przelewu ISO20022<ept id="p1">](./tasks/set-up-company-bank-accounts-iso20022-credit-transfers.md)</ept></target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="200">
          <source><bpt id="p1">[</bpt>Set up company bank accounts for ISO20022 direct debits<ept id="p1">](./tasks/set-up-company-bank-accounts-iso20022-direct-debits.md)</ept></source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm"><bpt id="p1">[</bpt>Konfigurowanie kont bankowych firmy dla poleceń zapłaty ISO20022<ept id="p1">](./tasks/set-up-company-bank-accounts-iso20022-direct-debits.md)</ept></target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="201">
          <source><bpt id="p1">[</bpt>Set up customers and customer bank accounts for ISO20022 direct debits<ept id="p1">](./tasks/set-up-bank-accounts-iso20022-direct-debits.md)</ept></source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm"><bpt id="p1">[</bpt>Konfigurowanie odbiorców i kont bankowych odbiorców dla poleceń zapłaty ISO20022<ept id="p1">](./tasks/set-up-bank-accounts-iso20022-direct-debits.md)</ept></target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="202">
          <source><bpt id="p1">[</bpt>Set up method of payment for ISO20022 credit transfer<ept id="p1">](./tasks/set-up-method-payment-iso20022-credit-transfer.md)</ept></source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm"><bpt id="p1">[</bpt>Konfigurowanie metody płatności przelewu ISO20022<ept id="p1">](./tasks/set-up-method-payment-iso20022-credit-transfer.md)</ept></target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="203">
          <source><bpt id="p1">[</bpt>Set up method of payment for ISO20022 direct debit<ept id="p1">](./tasks/setup-method-payment-iso20022-direct-debit.md)</ept></source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm"><bpt id="p1">[</bpt>Konfigurowanie metody płatności polecenia zapłaty ISO20022<ept id="p1">](./tasks/setup-method-payment-iso20022-direct-debit.md)</ept></target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="204">
          <source><bpt id="p1">[</bpt>Set up vendors and vendor bank accounts for ISO20022 credit transfers<ept id="p1">](./tasks/set-up-vendor-iso20022-credit-transfers.md)</ept></source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm"><bpt id="p1">[</bpt>Konfigurowanie dostawców i kont bankowych dostawców dla poleceń przelewu ISO20022<ept id="p1">](./tasks/set-up-vendor-iso20022-credit-transfers.md)</ept></target></trans-unit>
      </group>
    </body>
  </file>
</xliff>