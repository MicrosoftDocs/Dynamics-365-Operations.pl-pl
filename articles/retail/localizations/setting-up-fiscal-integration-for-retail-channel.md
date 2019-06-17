<?xml version="1.0" encoding="UTF-8"?>
<xliff xmlns:logoport="urn:logoport:xliffeditor:xliff-extras:1.0" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns="urn:oasis:names:tc:xliff:document:1.2" xmlns:xliffext="urn:microsoft:content:schema:xliffextensions" version="1.2" xsi:schemaLocation="urn:oasis:names:tc:xliff:document:1.2 xliff-core-1.2-transitional.xsd">
  <file datatype="xml" source-language="en-US" original="setting-up-fiscal-integration-for-retail-channel.md" target-language="pl-PL">
    <header>
      <tool tool-company="Microsoft" tool-version="1.0-7889195" tool-name="mdxliff" tool-id="mdxliff"/>
      <xliffext:skl_file_name>setting-up-fiscal-integration-for-retail-channel.bcaf21.fda94e77480b9d9455fc0e214e43772ab2921f2d.skl</xliffext:skl_file_name>
      <xliffext:version>1.2</xliffext:version>
      <xliffext:ms.openlocfilehash>fda94e77480b9d9455fc0e214e43772ab2921f2d</xliffext:ms.openlocfilehash>
      <xliffext:ms.sourcegitcommit>ffc37f7c2a63bada3055f37856a30424040bc9a3</xliffext:ms.sourcegitcommit>
      <xliffext:ms.lasthandoff>05/16/2019</xliffext:ms.lasthandoff>
      <xliffext:ms.openlocfilepath>articles\retail\localizations\setting-up-fiscal-integration-for-retail-channel.md</xliffext:ms.openlocfilepath>
    </header>
    <body>
      <group extype="content" id="content">
        <trans-unit xml:space="preserve" translate="yes" id="101" restype="x-metadata">
          <source>Set up the fiscal integration for Retail channels</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Konfigurowanie integracji fiskalnej dla kanałów sprzedaży detalicznej</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="102" restype="x-metadata">
          <source>This topic provides guidelines for setting up the fiscal integration functionality for Retail channels.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">W tym temacie zawarto wskazówki dotyczące konfigurowania funkcji integracji fiskalnej dla kanałów sprzedaży detalicznej.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="103">
          <source>Set up the fiscal integration for Retail channels</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Konfigurowanie integracji fiskalnej dla kanałów sprzedaży detalicznej</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="104">
          <source>Introduction</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Wprowadzenie</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="105">
          <source>This topic provides guidelines for setting up the fiscal integration functionality for Retail channels.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">W tym temacie zawarto wskazówki dotyczące konfigurowania funkcji integracji fiskalnej dla kanałów sprzedaży detalicznej.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="106">
          <source>For more information about the fiscal integration, see <bpt id="p1">[</bpt>Overview of fiscal integration for Retail channels<ept id="p1">](fiscal-integration-for-retail-channel.md)</ept>.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Aby uzyskać więcej informacji o integracji fiskalnej, zobacz <bpt id="p1">[</bpt>Omówienie integracji fiskalnej dla kanałów sprzedaży detalicznej z<ept id="p1">](fiscal-integration-for-retail-channel.md)</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="107">
          <source>The process of setting up the fiscal integration includes the following tasks:</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Proces konfigurowania integracji fiskalnej obejmuje następujące zadania:</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="108">
          <source>Configure fiscal connectors that represent fiscal devices or services that are used for fiscal registration purposes, such as fiscal printers.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Konfigurowanie łączników fiskalnych dla urządzeń lub usług fiskalnych używanych do celów rejestracji fiskalnej, np. drukarki fiskalne.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="109">
          <source>Configure document providers that generate fiscal documents that will be registered in fiscal devices or services by fiscal connectors.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Konfigurowanie dostawców dokumentu, generujących dokumenty fiskalne, którzy będą zarejestrowani w urządzeniach lub usługach fiskalnych przez łączniki fiskalne.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="110">
          <source>Configure the fiscal registration process that defines a sequence of fiscal registration steps and the fiscal connectors and fiscal document providers that are used for each step.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Konfigurowanie procesu rejestracji fiskalnej, który określa sekwencję kroków fiskalnych oraz łączników fiskalnych i dostawców dokumentów fiskalnych używanych w każdym kroku.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="111">
          <source>Assign the fiscal registration process to point of sale (POS) functionality profiles.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Przypisywanie procesu rejestracji fiskalnej do profili funkcji POS.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="112">
          <source>Assign connector technical profiles to hardware profiles.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Przypisywanie profili technicznych łącznika do profili sprzętowych.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="113">
          <source>Set up a fiscal registration process</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Konfigurowanie procesu rejestracji fiskalnej</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="114">
          <source>Before you use the fiscal integration functionality, you should configure the following settings.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Przed użyciem funkcji integracji fiskalnej należy skonfigurować następujące ustawienia.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="115">
          <source>Update retail parameters.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Aktualizacja parametrów sieci sprzedaży.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="116">
          <source>On the <bpt id="p1">**</bpt>Retail shared parameters<ept id="p1">**</ept> page, on the <bpt id="p2">**</bpt>General<ept id="p2">**</ept> tab, set the <bpt id="p3">**</bpt>Enable fiscal integration<ept id="p3">**</ept> option to <bpt id="p4">**</bpt>Yes<ept id="p4">**</ept>.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Na stronie <bpt id="p1">**</bpt>Wspólne parametry sieci sprzedaży<ept id="p1">**</ept> na karcie <bpt id="p2">**</bpt>Ogólne<ept id="p2">**</ept> ustaw opcję <bpt id="p3">**</bpt>Włącz integrację fiskalną<ept id="p3">**</ept> na <bpt id="p4">**</bpt>Tak<ept id="p4">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="117">
          <source>On the <bpt id="p1">**</bpt>Number sequences<ept id="p1">**</ept> tab, define the number sequences for the following references:</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Na karcie <bpt id="p1">**</bpt>Sekwencje identyfikatorów<ept id="p1">**</ept> zdefiniuj sekwencję numerów dla następujących odwołań:</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="118">
          <source>Fiscal technical profile number</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Identyfikator fiskalnego profilu technicznego</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="119">
          <source>Fiscal connector group number</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Identyfikator grupy łącznika fiskalnego</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="120">
          <source>Registration process number</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Identyfikator procesu rejestracji</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="121">
          <source>On the <bpt id="p1">**</bpt>Retail parameters<ept id="p1">**</ept> page, define the number sequence for the fiscal functional profile number.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Na stronie <bpt id="p1">**</bpt>Parametry sieci sprzedaży<ept id="p1">**</ept> zdefiniuj sekwencję numerów dla fiskalnego profilu funkcjonalności.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="122">
          <source>Number sequences are optional.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Sekwencje numerów są opcjonalne.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="123">
          <source>Numbers for all fiscal integration entities can be generated either from number sequences or manually.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Numery dla wszystkich jednostek integracji fiskalnej mogą być generowane z sekwencji numerów albo ręcznie.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="124">
          <source>Upload configurations of fiscal connectors and fiscal document providers.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Prześlij konfiguracje łączników fiskalnych i dostawców dokumentów fiskalnych.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="125">
          <source>A fiscal document provider is responsible for generating fiscal documents that represent retail transactions and events that are registered on the POS in a format that is also used for the interaction with a fiscal device or service.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Dostawca dokumentów fiskalnych jest odpowiedzialny za generowanie dokumentów fiskalnych, które reprezentują transakcję sieci sprzedaży oraz zdarzenia, które są rejestrowane w POS w formacie, który służy do interakcji z urządzeniem fiskalnym lub usługą fiskalną.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="126">
          <source>For example, a fiscal document provider might generate a representation of a fiscal receipt in an XML format.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Na przykład dostawca dokumentu fiskalnego może wygenerować reprezentację paragonu fiskalnego w formacie XML.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="127">
          <source>A fiscal connector is responsible for the communication with a fiscal device or service.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Łącznik fiskalny jest odpowiedzialny za komunikację z urządzeniem fiskalnym lub usługą fiskalną.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="128">
          <source>For example, a fiscal connector might send a fiscal receipt that a fiscal document provider created in an XML format to a fiscal printer.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Na przykład łącznik fiskalny może wysłać paragon fiskalny utworzony przez dostawcę dokumentu fiskalnego w formacie XML na drukarce fiskalnej.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="129">
          <source>For more details about fiscal integration components, see <bpt id="p1">[</bpt>Fiscal registration process and fiscal integration samples for fiscal devices<ept id="p1">](fiscal-integration-for-retail-channel.md#fiscal-registration-process-and-fiscal-integration-samples-for-fiscal-devices)</ept>.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Aby uzyskać więcej informacji o komponentach integracji fiskalnej, zobacz <bpt id="p1">[</bpt>Proces rejestracji fiskalnej i przykłady integracji fiskalnej dla urządzeń fiskalnych<ept id="p1">](fiscal-integration-for-retail-channel.md#fiscal-registration-process-and-fiscal-integration-samples-for-fiscal-devices)</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="130">
          <source>On the <bpt id="p1">**</bpt>Fiscal connectors<ept id="p1">**</ept> page (<bpt id="p2">**</bpt>Retail <ph id="ph1">\&gt;</ph> Channel setup <ph id="ph2">\&gt;</ph> Fiscal integration <ph id="ph3">\&gt;</ph> Fiscal connectors<ept id="p2">**</ept>), upload an XML configuration for each device or service that you plan to use for fiscal integration purposes.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Na stronie <bpt id="p1">**</bpt>Łączniki fiskalne<ept id="p1">**</ept> (<bpt id="p2">**</bpt>Handel detaliczny<ph id="ph1">\&gt;</ph> Ustawienia kanału <ph id="ph2">\&gt;</ph> Integracja fiskalna <ph id="ph3">\&gt;</ph> Łączniki fiskalne<ept id="p2">**</ept>) prześlij konfigurację XML dla każdego urządzenia lub usługi, których planujesz używać na potrzeby integracji fiskalnej.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="131">
          <source>By selecting <bpt id="p1">**</bpt>View<ept id="p1">**</ept>, you can view all functional and technical profiles that are related to the current fiscal connector.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Wybierając <bpt id="p1">**</bpt>Widok<ept id="p1">**</ept>, można wyświetlić wszystkie funkcjonalne i techniczne profile, które odnoszą się do bieżącego łącznika fiskalnego.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="132">
          <source>On the <bpt id="p1">**</bpt>Fiscal document providers<ept id="p1">**</ept> page (<bpt id="p2">**</bpt>Retail <ph id="ph1">\&gt;</ph> Channel setup <ph id="ph2">\&gt;</ph> Fiscal integration <ph id="ph3">\&gt;</ph> Fiscal document providers<ept id="p2">**</ept>), upload an XML configuration for each device or service that you plan to use.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Na stronie <bpt id="p1">**</bpt>Dostawcy dokumentów fiskalnych<ept id="p1">**</ept> (<bpt id="p2">**</bpt>Handel detaliczny<ph id="ph1">\&gt;</ph> Ustawienia kanału <ph id="ph2">\&gt;</ph> Integracja fiskalna <ph id="ph3">\&gt;</ph> Dostawcy dokumentów fiskalnych<ept id="p2">**</ept>) prześlij konfigurację XML dla każdego urządzenia lub usługi, których planujesz używać.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="133">
          <source>By selecting <bpt id="p1">**</bpt>View<ept id="p1">**</ept>, you can view all functional profiles that are related to the current fiscal document provider.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Wybierając <bpt id="p1">**</bpt>Widok<ept id="p1">**</ept>, można wyświetlić wszystkie funkcjonalne profile, które odnoszą się do bieżącego dostawcy dokumentów fiskalnych.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="134">
          <source>For examples of configurations of fiscal connectors and fiscal document providers, see <bpt id="p1">[</bpt>Fiscal integration samples in the Retail SDK<ept id="p1">](fiscal-integration-for-retail-channel.md#fiscal-integration-samples-in-the-retail-sdk)</ept>.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Przykładowe konfiguracje łączników fiskalnych i dostawców dokumentów fiskalnych, zobacz <bpt id="p1">[</bpt>Przykłady integracji fiskalnej w zestawie SDK modułu Retail<ept id="p1">](fiscal-integration-for-retail-channel.md#fiscal-integration-samples-in-the-retail-sdk)</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="135">
          <source>Data mapping is considered part of a fiscal document provider.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Mapowanie danych jest uważane za element dostawcy dokumentów fiskalnych.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="136">
          <source>To set up different data mappings for the same connector (for example, state-specific regulations), you should create different fiscal document providers.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Aby skonfigurować inne mapowania danych dla tego samego łącznika (np. do obsługi szczególnych przepisów stanowych), należy utworzyć innych dostawców dokumentów fiskalnych.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="137">
          <source>Create connector functional profiles and connector technical profiles.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Tworzenie profili funkcjonalnych i technicznych łącznika.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="138">
          <source>On the <bpt id="p1">**</bpt>Connector functional profiles<ept id="p1">**</ept> page (<bpt id="p2">**</bpt>Retail <ph id="ph1">\&gt;</ph> Channel setup <ph id="ph2">\&gt;</ph> Fiscal integration <ph id="ph3">\&gt;</ph> Connector functional profiles<ept id="p2">**</ept>), create a connector functional profile for each combination of a fiscal connector and a fiscal document provider that is related to this fiscal connector.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Na stronie <bpt id="p1">**</bpt>Profile funkcjonalne łącznika<ept id="p1">**</ept> (<bpt id="p2">**</bpt>Handel detaliczny <ph id="ph1">\&gt;</ph> Konfiguracja kanału <ph id="ph2">\&gt;</ph> Integracja fiskalna <ph id="ph3">\&gt;</ph> Profile funkcjonalne łącznika<ept id="p2">**</ept>) utwórz profil funkcjonalny łącznika dla każdej kombinacji łącznika fiskalnego i dostawcy dokumentów fiskalnych, która jest związana z tym łącznikiem fiskalnym.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="139">
          <source>Select a connector name.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Nazwij łącznik.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="140">
          <source>Select a document provider.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Wybierz dostawcę dokumentów.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="141">
          <source>You can change the data mapping parameters in a connector functional profile.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Można zmienić parametry mapowania danych w profilu funkcjonalnym łącznika.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="142">
          <source>To restore the default parameters that are defined in the fiscal document provider configuration, select <bpt id="p1">**</bpt>Update<ept id="p1">**</ept>.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Aby przywrócić domyślne parametry zdefiniowane w konfiguracji dostawcy dokumentów fiskalnych, wybierz <bpt id="p1">**</bpt>Zaktualizuj<ept id="p1">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="143">
          <source><bpt id="p1">**</bpt>Examples<ept id="p1">**</ept></source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm"><bpt id="p1">**</bpt>Przykłady<ept id="p1">**</ept></target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="144">
          <source>Format</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Format</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="145">
          <source>Example</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Przykład</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="146">
          <source><bpt id="p1">**</bpt>VAT rates settings<ept id="p1">**</ept></source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm"><bpt id="p1">**</bpt>Ustawienia stawek podatku VAT<ept id="p1">**</ept></target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="147">
          <source>value : VATrate</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">wartość : VATrate</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="148">
          <source>1 : 2000, 2 : 1800</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">1 : 2000, 2 : 1800</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="149">
          <source><bpt id="p1">**</bpt>VAT codes mapping<ept id="p1">**</ept></source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm"><bpt id="p1">**</bpt>Mapowanie kodów VAT<ept id="p1">**</ept></target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="150">
          <source>VATcode : value</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">VATcode : wartość</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="151">
          <source>vat20 : 1, vat18 : 2</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">vat20 : 1, vat18 : 2</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="152">
          <source><bpt id="p1">**</bpt>Tender types mapping<ept id="p1">**</ept></source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm"><bpt id="p1">**</bpt>Mapowanie typów metod płatności<ept id="p1">**</ept></target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="153">
          <source>TenderType : value</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">TenderType : wartość</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="154">
          <source>Cash : 1, Card : 2</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Gotówka : 1, Karta : 2</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="155">
          <source>Connector functional profiles are company-specific.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Profile funkcjonalne łącznika są specyficzne dla firmy.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="156">
          <source>If you plan to use the same combination of a fiscal connector and a fiscal document provider in different companies, you should create a connector functional profile for each company.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Jeśli użytkownik chce używać tej samej kombinacji łącznika fiskalnego i dostawcy dokumentów fiskalnych w różnych firmach, należy utworzyć profil funkcjonalny łącznika dla każdej firmy.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="157">
          <source>On the <bpt id="p1">**</bpt>Connector technical profiles<ept id="p1">**</ept> page (<bpt id="p2">**</bpt>Retail <ph id="ph1">\&gt;</ph> Channel setup <ph id="ph2">\&gt;</ph> Fiscal integration <ph id="ph3">\&gt;</ph> Connector technical profiles<ept id="p2">**</ept>), create a connector technical profile for each fiscal connector.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Na stronie <bpt id="p1">**</bpt>Profile techniczne łącznia<ept id="p1">**</ept> (<bpt id="p2">**</bpt>Handel detaliczny <ph id="ph1">\&gt;</ph> Ustawienia kanału <ph id="ph2">\&gt;</ph> Integracja fiskalna <ph id="ph3">\&gt;</ph> Profile techniczne łącznika<ept id="p2">**</ept>) utwórz profil techniczny łącznika dla każdego łącznika fiskalnego.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="158">
          <source>Select a connector name.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Nazwij łącznik.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="159">
          <source>Select a connector type.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Wybierz typ łącznika.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="160">
          <source>For devices that are connected to a Hardware station, select <bpt id="p1">**</bpt>Local<ept id="p1">**</ept>.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Dla urządzeń, które są połączone z Hardware Station, zaznacz opcję <bpt id="p1">**</bpt>Lokalne<ept id="p1">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="161">
          <source>Only local connectors are currently supported.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Obecnie obsługiwane są tylko łączniki lokalne.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="162">
          <source>Parameters on the <bpt id="p1">**</bpt>Device<ept id="p1">**</ept> and <bpt id="p2">**</bpt>Settings<ept id="p2">**</ept> tabs in a connector technical profile can be changed.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Parametry na kartach <bpt id="p1">**</bpt>Urządzenie<ept id="p1">**</ept> i <bpt id="p2">**</bpt>Ustawienia<ept id="p2">**</ept> w profilu technicznym łącznika można zmienić.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="163">
          <source>To restore the default parameters that are defined in the fiscal connector configuration, select <bpt id="p1">**</bpt>Update<ept id="p1">**</ept>.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Aby przywrócić domyślne parametry zdefiniowane w konfiguracji łącznika fiskalnego, wybierz <bpt id="p1">**</bpt>Zaktualizuj<ept id="p1">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="164">
          <source>While a new version of an XML configuration is loaded, you receive a message that states that the current fiscal connector or fiscal document provider is already being used.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Kiedy zostanie załadowana nowa wersja konfiguracji XML, otrzymasz komunikat informujący, że bieżący łącznik fiskalny lub dostawca dokumentów fiskalnych są już używane.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="165">
          <source>This procedure doesn't override manual changes that were previously made in connector functional profiles and connector technical profiles.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Ta procedura nie zastępuje zmian wprowadzonych ręcznie wcześniej w profilach funkcjonalnych łączników i profilach technicznych łączników.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="166">
          <source>To apply the default set of parameters from a new configuration, on the <bpt id="p1">**</bpt>Connector functional profiles<ept id="p1">**</ept> page or the <bpt id="p2">**</bpt>Connector technical profiles<ept id="p2">**</ept> page, select <bpt id="p3">**</bpt>Update<ept id="p3">**</ept>.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Aby zastosować domyślny zestaw parametrów z nowej konfiguracji na stronie <bpt id="p1">**</bpt>Profile funkcjonalne łącznika<ept id="p1">**</ept> lub <bpt id="p2">**</bpt>Profile techniczne łącznika<ept id="p2">**</ept>, wybierz <bpt id="p3">**</bpt>Aktualizuj<ept id="p3">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="167">
          <source>Create fiscal connector groups.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Tworzenie grup łączników fiskalnych.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="168">
          <source>A fiscal connector group combines functional profiles of fiscal connectors that perform identical functions and are used at the same step of a fiscal registration process.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Grupa łączników fiskalnych łączy profile funkcjonalne łączników fiskalnych, które wykonują te same funkcje i są używane na tym samym etapie procesu rejestracji fiskalnej.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="169">
          <source>For example, if several fiscal printer models can be used in a retail store, fiscal connectors for those fiscal printers can be combined in a fiscal connector group.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Na przykład jeśli kilka modeli drukarki fiskalnej może być używanych w sklepie detalicznym, łączniki fiskalne dla tych drukarek fiskalnych mogą być połączone w grupie łączników fiskalnych.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="170">
          <source>On the <bpt id="p1">**</bpt>Fiscal connector group<ept id="p1">**</ept> page (<bpt id="p2">**</bpt>Retail <ph id="ph1">\&gt;</ph> Channel setup <ph id="ph2">\&gt;</ph> Fiscal integration <ph id="ph3">\&gt;</ph> Fiscal connector groups<ept id="p2">**</ept>), create a new fiscal connector group.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Na stronie <bpt id="p1">**</bpt>Grupa łączników fiskalnych<ept id="p1">**</ept> (<bpt id="p2">**</bpt>Handel detaliczny <ph id="ph1">\&gt;</ph> Ustawienia kanału <ph id="ph2">\&gt;</ph> Integracja fiskalna <ph id="ph3">\&gt;</ph> Grupy łączników fiskalnych<ept id="p2">**</ept>) utwórz nową grupę łączników fiskalnych.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="171">
          <source>Add functional profiles to the connector group.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Dodaj profile funkcjonalności do grupy łączników.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="172">
          <source>On the <bpt id="p1">**</bpt>Functional profiles<ept id="p1">**</ept> tab, select <bpt id="p2">**</bpt>Add<ept id="p2">**</ept>, and select a profile number.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Na karcie <bpt id="p1">**</bpt>Profile funkcjonalne<ept id="p1">**</ept> wybierz <bpt id="p2">**</bpt>Dodaj<ept id="p2">**</ept> i wybierz numer profilu.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="173">
          <source>Each fiscal connector in a connector group can only have one functional profile.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Każdy łącznik fiskalny w grupie łączników może mieć tylko jeden profil funkcjonalności.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="174">
          <source>To suspend use of the functional profile, set the <bpt id="p1">**</bpt>Disable<ept id="p1">**</ept> option to <bpt id="p2">**</bpt>Yes<ept id="p2">**</ept>.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Aby zawiesić używanie profilu funkcjonalności, ustaw opcję <bpt id="p1">**</bpt>Wyłącz<ept id="p1">**</ept> na wartość <bpt id="p2">**</bpt>Tak<ept id="p2">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="175">
          <source>This change affects only the current connector group.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Ta zmiana dotyczy tylko bieżącej grupy łączników.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="176">
          <source>You can continue to use the same functional profile in other connector groups.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Możesz kontynuować używanie tego samego profilu funkcjonalności w innych grupach łączników.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="177">
          <source>Create a fiscal registration process.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Tworzenie procesu rejestracji fiskalnej.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="178">
          <source>A fiscal registration process is defined by the sequence of registration steps and the connector group that is used for each step.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Proces rejestracji fiskalnej jest definiowany przez sekwencję etapów rejestracji oraz przez grupę łączników używaną na każdym etapie.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="179">
          <source>On the <bpt id="p1">**</bpt>Fiscal registration process<ept id="p1">**</ept> page (<bpt id="p2">**</bpt>Retail <ph id="ph1">\&gt;</ph> Channel setup <ph id="ph2">\&gt;</ph> Fiscal integration <ph id="ph3">\&gt;</ph> Fiscal registration processes<ept id="p2">**</ept>), create a new record for each unique process of fiscal registration.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Na stronie <bpt id="p1">**</bpt>Proces rejestracji fiskalnej<ept id="p1">**</ept> (<bpt id="p2">**</bpt>Handel detaliczny <ph id="ph1">\&gt;</ph> Ustawienia kanału <ph id="ph2">\&gt;</ph> Integracja fiskalna <ph id="ph3">\&gt;</ph> Procesy rejestracji fiskalnych<ept id="p2">**</ept>) utwórz nowy rekord dla każdego unikatowego procesu rejestracji fiskalnej.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="180">
          <source>Add registration steps to the process:</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Dodaj etapy rejestracji do procesu:</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="181">
          <source>Select <bpt id="p1">**</bpt>Add<ept id="p1">**</ept>.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Wybierz opcję <bpt id="p1">**</bpt>Dodaj<ept id="p1">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="182">
          <source>Select a fiscal connector type.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Wybierz typ łącznika fiskalnego:</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="183">
          <source>In the <bpt id="p1">**</bpt>Group number<ept id="p1">**</ept> field, select an appropriate fiscal connector group.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">W polu <bpt id="p1">**</bpt>Numer grupy<ept id="p1">**</ept> wybierz odpowiedni grupę łączników fiskalnych.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="184">
          <source>Assign entities of the fiscal registration process to POS profiles.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Przypisz jednostki procesu rejestracji fiskalnej do profili POS.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="185">
          <source>On the <bpt id="p1">**</bpt>POS functionality profiles<ept id="p1">**</ept> page (<bpt id="p2">**</bpt>Retail <ph id="ph1">\&gt;</ph> Channel setup <ph id="ph2">\&gt;</ph> POS setup <ph id="ph3">\&gt;</ph> POS profiles <ph id="ph4">\&gt;</ph> Functionality profiles<ept id="p2">**</ept>), assign the fiscal registration process to a POS functionality profile.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Na stronie <bpt id="p1">**</bpt>Profile funkcjonalne POS<ept id="p1">**</ept> (<bpt id="p2">**</bpt>Handel detaliczny <ph id="ph1">\&gt;</ph> Ustawienia kanału <ph id="ph2">\&gt;</ph> Ustawienia POS <ph id="ph3">\&gt;</ph> Profile POS <ph id="ph4">\&gt;</ph> Profile funkcjonalności<ept id="p2">**</ept>) przypisz proces rejestracji fiskalnej do profilu funkcjonalności POS.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="186">
          <source>Select <bpt id="p1">**</bpt>Edit<ept id="p1">**</ept>, and then, on the <bpt id="p2">**</bpt>Fiscal registration process<ept id="p2">**</ept> tab, in the <bpt id="p3">**</bpt>Process number<ept id="p3">**</ept> field, select a process.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Wybierz <bpt id="p1">**</bpt>Edytuj<ept id="p1">**</ept>, a następnie na karcie <bpt id="p2">**</bpt>Proces rejestracji fiskalnej<ept id="p2">**</ept> w polu <bpt id="p3">**</bpt>Numer procesu<ept id="p3">**</ept> wybierz proces.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="187">
          <source>On the <bpt id="p1">**</bpt>POS hardware profile<ept id="p1">**</ept> page (<bpt id="p2">**</bpt>Retail <ph id="ph1">\&gt;</ph> Channel setup <ph id="ph2">\&gt;</ph> POS setup <ph id="ph3">\&gt;</ph> POS profiles <ph id="ph4">\&gt;</ph> Hardware profiles<ept id="p2">**</ept>), assign connector technical profiles to a hardware profile.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Na stronie <bpt id="p1">**</bpt>Profil sprzętu POS<ept id="p1">**</ept> (<bpt id="p2">**</bpt>Handel detaliczny <ph id="ph1">\&gt;</ph> Ustawienia kanału <ph id="ph2">\&gt;</ph> Ustawienia POS <ph id="ph3">\&gt;</ph> Profile POS <ph id="ph4">\&gt;</ph> Profile sprzętowe<ept id="p2">**</ept>) przydziel profile techniczne łącznika do profilu sprzętowego.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="188">
          <source>Select <bpt id="p1">**</bpt>Edit<ept id="p1">**</ept>, add a line on the <bpt id="p2">**</bpt>Fiscal peripherals<ept id="p2">**</ept> tab, and then, in the <bpt id="p3">**</bpt>Profile number<ept id="p3">**</ept> field, select a connector technical profile.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Wybierz <bpt id="p1">**</bpt>Edytuj<ept id="p1">**</ept> dodaj wiersz do karty <bpt id="p2">**</bpt>Peryferyjne urządzenia fiskalne<ept id="p2">**</ept>, a następnie w polu <bpt id="p3">**</bpt>Numer profilu<ept id="p3">**</ept> wybierz profil techniczny łącznika.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="189">
          <source>You can add several technical profiles to the same hardware profile.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Do tego samego profilu sprzętowego można dodać kilka profili technicznych.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="190">
          <source>However, a hardware profile or POS functionality profile should have only one intersection with any fiscal connector group.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Jednak profil sprzętowy lub profil funkcjonalności POS powinny mieć tylko jeden punkt styczny z grupą łączników fiskalnych.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="191">
          <source>The fiscal registration flow is defined by the fiscal registration process and also by some parameters of fiscal integration components: the Commerce runtime extension for the fiscal document provider and the Hardware station extension for the fiscal connector.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Przepływ rejestracji fiskalnej jest definiowany przez proces rejestracji fiskalnej i również przez niektóre parametry komponentów integracji fiskalnej: wykonanie środowiska uruchomieniowego Commerce dla dostawcy dokumentów fiskalncych oraz wykonanie Hardware Station dla łącznika fiskalnego.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="192">
          <source>The subscription of events and transactions to fiscal registration is predefined in the fiscal document provider.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Subskrypcja zdarzeń i transakcji w rejestracji fiskalnej jest wstępnie zdefiniowana w dostawcy dokumentów fiskalnych.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="193">
          <source>The fiscal document provider is also responsible for identifying the fiscal connector that is used for fiscal registration.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Dostawca dokumentów fiskalnych jest również odpowiedzialny za identyfikację łącznika fiskalnego używanego do rejestracji fiskalnej.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="194">
          <source>It matches the connector functional profiles that are included in the fiscal connector group that is specified for the current step of the fiscal registration process with the connector technical profile that is assigned to the hardware profile of the Hardware station that the POS is paired to.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Jest on zgodny z profilami funkcjonalnymi łącznika, które są uwzględniane w grupie łączników fiskalnych, określonych dla bieżącego kroku procesu rejestracji fiskalnej z profilem technicznym łącznika, który jest skojarzony z profilem sprzętowym Hardware Station, z którą jest sparowany POS.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="195">
          <source>The fiscal document provider uses the data mapping settings from the fiscal document provider configuration to transform transaction/event data such as taxes and payments while a fiscal document is generated.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Dostawca dokumentów fiskalnych korzysta z ustawień mapowania danych z konfiguracji dostawcy dokumentów fiskalnych do przekształcania danych transakcji/zdarzeń na podatki i płatności podczas generowania dokumentu fiskalnego.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="196">
          <source>When the fiscal document provider generates a fiscal document, the fiscal connector can either send it to the fiscal device as is, or parse it and transform it into a sequence of commands of the device application programming interface (API), depending on how the communication is handled.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Kiedy dostawca dokumentów fiskalnych generuje dokument fiskalny, łącznik fiskalny może albo wysłać go do urządzenia fiskalnego bez zmian, albo przeanalizować go i zamienić na sekwencję poleceń interfejsu API - to zależy od tego, jak obsługiwana jest komunikacja.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="197">
          <source>On the <bpt id="p1">**</bpt>Fiscal registration process<ept id="p1">**</ept> page (<bpt id="p2">**</bpt>Retail <ph id="ph1">\&gt;</ph> Channel setup <ph id="ph2">\&gt;</ph> Fiscal integration <ph id="ph3">\&gt;</ph> Fiscal registration processes<ept id="p2">**</ept>), select <bpt id="p3">**</bpt>Validate<ept id="p3">**</ept> to validate the fiscal registration process.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Na stronie <bpt id="p1">**</bpt>Proces rejestracji fiskalnej<ept id="p1">**</ept> (<bpt id="p2">**</bpt>Handel detaliczny <ph id="ph1">\&gt;</ph> Ustawienia kanału <ph id="ph2">\&gt;</ph> Integracja fiskalna <ph id="ph3">\&gt;</ph> Procesy rejestracji fiskalnych<ept id="p2">**</ept>) wybierz <bpt id="p3">**</bpt>Sprawdź<ept id="p3">**</ept>, aby sprawdzić proces rejestracji fiskalnej.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="198">
          <source>We recommend that you run this type of validation in the following cases:</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Zalecamy uruchomienie tego typu weryfikacji w następujących przypadkach:</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="199">
          <source>After you've completed all the settings for a new registration process, including when you assign registration processes to POS functionality profiles and hardware profiles.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Po zakończeniu wprowadzania wszystkich ustawień dla nowego procesu rejestracji, w tym podczas przypisywania procesu rejestracji do profili funkcjonalności POS i profili sprzętowych.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="200">
          <source>After you make changes to an existing fiscal registration process, and those changes might cause a different fiscal connector to be selected at runtime (for example, if you change the connector group for a fiscal registration process step, enable a connector functional profile in a connector group, or add a new connector functional profile to a connector group).</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Po wprowadzeniu zmian do istniejącego procesu rejestracji fiskalnej i kiedy te zmiany mogą powodować wybieranie różnych łączników fiskalnych w momencie uruchomienia (np. jeśli zmienisz grupę łączników dla konfiguracji procesu rejestracji fiskalnej, włączysz profil funkcjonalny łącznika w grupie łączników lub dodasz nowy profil funkcjonalny do grupy łączników).</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="201">
          <source>After you make changes in the assignment of connector technical profiles to hardware profiles.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Po wprowadzeniu zmian w przypisaniu profilów technicznych łącznika do profilów sprzętowych.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="202">
          <source>On the <bpt id="p1">**</bpt>Distribution schedule<ept id="p1">**</ept> page, run the <bpt id="p2">**</bpt>1070<ept id="p2">**</ept> and <bpt id="p3">**</bpt>1090<ept id="p3">**</ept> jobs to transfer data to the channel database.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Na stronie <bpt id="p1">**</bpt>Harmonogram dystrybucji<ept id="p1">**</ept> uruchom zadania <bpt id="p2">**</bpt>1070<ept id="p2">**</ept> i <bpt id="p3">**</bpt>1090<ept id="p3">**</ept>, aby przenieść dane do bazy danych kanału.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="203">
          <source>Set up fiscal texts for discounts</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Konfigurowanie tekstów fiskalnych dla rabatów</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="204">
          <source>In some cases, a special text must be printed on a fiscal receipt if a discount is applied.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">W niektórych przypadkach specjalny tekst musi zostać wydrukowany na paragonie fiskalnym, w przypadku zastosowania rabatu.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="205">
          <source>You can set up fiscal texts for discounts on the <bpt id="p1">**</bpt>Fiscal connector group<ept id="p1">**</ept> page (<bpt id="p2">**</bpt>Retail <ph id="ph1">\&gt;</ph> Channel setup <ph id="ph2">\&gt;</ph> Fiscal integration <ph id="ph3">\&gt;</ph> Fiscal connector groups<ept id="p2">**</ept>).</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Można skonfigurować teksty fiskalne dla rabatów na stronie <bpt id="p1">**</bpt>Grupa łączników fiskalnych<ept id="p1">**</ept> (<bpt id="p2">**</bpt>Handel detaliczny <ph id="ph1">\&gt;</ph> Ustawienia kanału <ph id="ph2">\&gt;</ph> Integracja fiskalna <ph id="ph3">\&gt;</ph> Grupy łączników fiskalnych<ept id="p2">**</ept>).</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="206">
          <source>For manual discounts that are applied at the POS, you should set a fiscal text for the info code or info code group that is specified as the <bpt id="p1">**</bpt>Product discount<ept id="p1">**</ept> info code in the POS functionality profile.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Dla rabatów ręcznych zastosowanych w POS musisz ustawić tekst fiskalny dla kodu informacyjnego lub grupy kodów informacji określonych jako kod informacji <bpt id="p1">**</bpt>Rabat produktu<ept id="p1">**</ept> w profilu funkcjonalności POS.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="207">
          <source>On the <bpt id="p1">**</bpt>Fiscal connector group<ept id="p1">**</ept> page, select <bpt id="p2">**</bpt>Text for fiscal receipt<ept id="p2">**</ept>.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Na stronie <bpt id="p1">**</bpt>Grupa łącznika fiskalnego<ept id="p1">**</ept> wybierz <bpt id="p2">**</bpt>Tekst paragonu fiskalnego<ept id="p2">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="208">
          <source>On the <bpt id="p1">**</bpt>Info codes<ept id="p1">**</ept> tab, select <bpt id="p2">**</bpt>Add<ept id="p2">**</ept>, and select an info code or info code group.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Na karcie <bpt id="p1">**</bpt>Kody informacji<ept id="p1">**</ept> wybierz <bpt id="p2">**</bpt>Dodaj<ept id="p2">**</ept> i wybierz kod informacji lub grupę kodów informacji.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="209">
          <source>In the <bpt id="p1">**</bpt>Info code number<ept id="p1">**</ept>, select a value.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">W polu <bpt id="p1">**</bpt>Numer kodu informacji<ept id="p1">**</ept> wybierz wartość.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="210">
          <source>In the <bpt id="p1">**</bpt>Subcode number<ept id="p1">**</ept> field, select a value if a subcode is required for the selected info code.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">W polu <bpt id="p1">**</bpt>Numer kodu podrzędnego<ept id="p1">**</ept> wybierz wartość, jeśli kod podrzędny jest wymagany dla wybranego kodu informacji.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="211">
          <source>In the <bpt id="p1">**</bpt>Text for fiscal receipt<ept id="p1">**</ept> field, specify a fiscal text that should be printed on a fiscal receipt.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">W polu <bpt id="p1">**</bpt>Tekst paragonu fiskalnego<ept id="p1">**</ept> określ tekst fiskalny, który ma być drukowany na paragonie fiskalnym.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="212">
          <source>Set the <bpt id="p1">**</bpt>Print user input on fiscal receipt<ept id="p1">**</ept> option to <bpt id="p2">**</bpt>Yes<ept id="p2">**</ept> to override the text on a fiscal receipt with information that a user manually enters at the POS.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Ustaw opcję <bpt id="p1">**</bpt>Drukuj tekst użytkownika na paragonie fiskalnym<ept id="p1">**</ept> na <bpt id="p2">**</bpt>Tak<ept id="p2">**</ept>, aby umożliwić zastąpienie tekstu na paragonie fiskalnym informacjami wprowadzanymi ręcznie przez użytkownika POS.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="213">
          <source>This option applies only to info codes that have an input type of <bpt id="p1">**</bpt>Text<ept id="p1">**</ept>.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Ta opcja dotyczy tylko kodów informacji, które mają typ danych wejściowych <bpt id="p1">**</bpt>Tekst<ept id="p1">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="214">
          <source>You can specify a fiscal text for several info codes to support scenarios where info code groups, linked info codes, and triggered info codes are used.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Można określić tekst fiskalny dla kilku kodów informacji, aby obsługiwać scenariusze, w których używane są grupy kodów informacji, połączone kody informacji i wywołane kody informacji.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="215">
          <source>In these scenarios, the fiscal receipt will contain the fiscal texts from all info codes that are linked to the transaction line where the discount was applied.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">W tych scenariuszach paragon fiskalny będzie zawierał tekst fiskalny z wszystkich kodów informacji połączonych z wierszem transakcji, w której zastosowano rabat.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="216">
          <source>For channel-specific discounts, you should define a fiscal text for the discount ID.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Dla rabatów specyficznych dla kanału należy zdefiniować tekst fiskalnych dla identyfikatora rabatu.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="217">
          <source>On the <bpt id="p1">**</bpt>Fiscal connector group<ept id="p1">**</ept> page, select <bpt id="p2">**</bpt>Text for fiscal receipt<ept id="p2">**</ept>.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Na stronie <bpt id="p1">**</bpt>Grupa łącznika fiskalnego<ept id="p1">**</ept> wybierz <bpt id="p2">**</bpt>Tekst paragonu fiskalnego<ept id="p2">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="218">
          <source>On the <bpt id="p1">**</bpt>Discounts<ept id="p1">**</ept> tab, select <bpt id="p2">**</bpt>Add<ept id="p2">**</ept>, and select a discount ID.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Na karcie <bpt id="p1">**</bpt>Rabaty<ept id="p1">**</ept> wybierz opcję <bpt id="p2">**</bpt>Dodaj<ept id="p2">**</ept> i wybierz identyfikator rabatu.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="219">
          <source>In the <bpt id="p1">**</bpt>Text for fiscal receipt<ept id="p1">**</ept> field, specify a fiscal text that should be printed on a fiscal receipt.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">W polu <bpt id="p1">**</bpt>Tekst paragonu fiskalnego<ept id="p1">**</ept> określ tekst fiskalny, który ma być drukowany na paragonie fiskalnym.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="220">
          <source>If several discounts are applied to the same transaction line, the fiscal receipt will contain fiscal texts from all discounts that are linked to those transaction line.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Jeśli kilka rabatów jest stosowanych do tego samego wiersza transakcji, paragon fiskalny będzie zawierał teksty fiskalne z wszystkich rabatów, które są połączone z tymi wierszami transakcji.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="221">
          <source>Set error handling settings</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Określanie ustawienia ustawień obsługi błędów</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="222">
          <source>The error handling options that are available in the fiscal integration are set in the fiscal registration process.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Opcje obsługi błędów dostępne w integracji fiskalnej ustawia się w procesie rejestracji fiskalnej.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="223">
          <source>For more information about error handling in the fiscal integration, see <bpt id="p1">[</bpt>Error handling<ept id="p1">](fiscal-integration-for-retail-channel.md#error-handling)</ept>.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Aby uzyskać więcej informacji na temat obsługi błędów w integracji fiskalnej, zobacz <bpt id="p1">[</bpt>Obsługa błędów<ept id="p1">](fiscal-integration-for-retail-channel.md#error-handling)</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="224">
          <source>On the <bpt id="p1">**</bpt>Fiscal registration process<ept id="p1">**</ept> page (<bpt id="p2">**</bpt>Retail <ph id="ph1">\&gt;</ph> Channel setup <ph id="ph2">\&gt;</ph> Fiscal integration <ph id="ph3">\&gt;</ph> Fiscal registration processes<ept id="p2">**</ept>), you can set the following parameters for each step of the fiscal registration process:</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Na stronie <bpt id="p1">**</bpt>Proces rejestracji fiskalnej<ept id="p1">**</ept> (<bpt id="p2">**</bpt>Handel detaliczny <ph id="ph1">\&gt;</ph> Ustawienia kanału <ph id="ph2">\&gt;</ph> Integracja fiskalna <ph id="ph3">\&gt;</ph> Procesy rejestracji fiskalnych<ept id="p2">**</ept>) możesz ustawić następujące parametry dla każdego kroku procesu rejestracji fiskalnej.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="225">
          <source><bpt id="p1">**</bpt>Allow skip<ept id="p1">**</ept> – This parameter enables the <bpt id="p2">**</bpt>Skip<ept id="p2">**</ept> option in the error handling dialog box.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm"><bpt id="p1">**</bpt>Zezwalaj na pomijanie<ept id="p1">**</ept> – ten parametr pozwala korzystać z opcji <bpt id="p2">**</bpt>Pomiń<ept id="p2">**</ept> w oknie dialogowym obsługi błędów.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="226">
          <source><bpt id="p1">**</bpt>Allow mark as registered<ept id="p1">**</ept> – This parameter enables the <bpt id="p2">**</bpt>Mark as registered<ept id="p2">**</ept> option in the error handling dialog box.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm"><bpt id="p1">**</bpt>Zezwalaj na oznaczanie jako zarejestrowane<ept id="p1">**</ept> — ten parametr umożliwia korzystanie z opcji <bpt id="p2">**</bpt>Oznacz jako zarejestrowane<ept id="p2">**</ept> w oknie dialogowym obsługi błędów.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="227">
          <source><bpt id="p1">**</bpt>Continue on error<ept id="p1">**</ept> – If this parameter is enabled, the fiscal registration process can continue on the POS register if the fiscal registration of a transaction or event fails.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm"><bpt id="p1">**</bpt>Kontynuuj przy błędzie<ept id="p1">**</ept> — Jeśli ten parametr jest włączony, proces rejestracji fiskalnej może być kontynuowany w rejestracji punktu sprzedaży po niepowodzeniu rejestracji transakcji lub zdarzenia.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="228">
          <source>Otherwise, to run the fiscal registration of the next transaction or event, the operator must retry the failed fiscal registration, skip it, or mark the transaction or event as registered.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">W przeciwnym razie do uruchomienia rejestracji fiskalnej następnej transakcji lub następnego zdarzenia operator musi podjąć ponowną próbę nieudanej rejestracji fiskalnej, pominąć ten krok lub oznaczyć transakcję lub zdarzenie jako zarejestrowane.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="229">
          <source>For more information, see <bpt id="p1">[</bpt>Optional fiscal registration<ept id="p1">](fiscal-integration-for-retail-channel.md#optional-fiscal-registration)</ept>.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Aby uzyskać więcej informacji, zobacz <bpt id="p1">[</bpt>Opcjonalna rejestracja fiskalna<ept id="p1">](fiscal-integration-for-retail-channel.md#optional-fiscal-registration)</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="230">
          <source>If the <bpt id="p1">**</bpt>Continue on error<ept id="p1">**</ept> parameter is enabled, the <bpt id="p2">**</bpt>Allow skip<ept id="p2">**</ept> and <bpt id="p3">**</bpt>Allow mark as registered<ept id="p3">**</ept> parameters are automatically disabled.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Po włączeniu parametru <bpt id="p1">**</bpt>Kontynuuj przy błędzie<ept id="p1">**</ept> parametry <bpt id="p2">**</bpt>Zezwalaj na pomijanie<ept id="p2">**</ept> i <bpt id="p3">**</bpt>Zezwalaj na oznaczanie jako zarejestrowane<ept id="p3">**</ept> są automatycznie wyłączone.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="231">
          <source>The <bpt id="p1">**</bpt>Skip<ept id="p1">**</ept> and <bpt id="p2">**</bpt>Mark as registered<ept id="p2">**</ept> options in the error handling dialog box require the <bpt id="p3">**</bpt>Allow skip registration or mark as registered<ept id="p3">**</ept> permission.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Opcje <bpt id="p1">**</bpt>Pomiń<ept id="p1">**</ept> i <bpt id="p2">**</bpt>Oznacz jako zarejestrowane<ept id="p2">**</ept> w oknie dialogowym obsługi błędów wymagają uprawnienia <bpt id="p3">**</bpt>Zezwalaj na pomijanie rejestracji lub oznaczanie jako zarejestrowane<ept id="p3">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="232">
          <source>Therefore, on the <bpt id="p1">**</bpt>Permission groups<ept id="p1">**</ept> page (<bpt id="p2">**</bpt>Retail <ph id="ph1">\&gt;</ph> Employees <ph id="ph2">\&gt;</ph> Permission groups<ept id="p2">**</ept>), enable the <bpt id="p3">**</bpt>Allow skip registration or mark as registered<ept id="p3">**</ept> permission.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Dlatego na stronie <bpt id="p1">**</bpt>Grupy uprawnień<ept id="p1">**</ept> (<bpt id="p2">**</bpt>Handel detaliczny <ph id="ph1">\&gt;</ph> Pracownicy <ph id="ph2">\&gt;</ph> Grupy uprawnień<ept id="p2">**</ept>) trzeba włączyć uprawnienie <bpt id="p3">**</bpt>Zezwalaj na pomijanie rejestracji lub oznaczanie jako zarejestrowane<ept id="p3">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="233">
          <source>The <bpt id="p1">**</bpt>Skip<ept id="p1">**</ept> and <bpt id="p2">**</bpt>Mark as registered<ept id="p2">**</ept> options let operators enter additional information when fiscal registration fails.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Opcje <bpt id="p1">**</bpt>Pomiń<ept id="p1">**</ept> i <bpt id="p2">**</bpt>Oznacz jako zarejestrowane<ept id="p2">**</ept> umożliwiają operatorom wprowadzanie dodatkowych informacji, kiedy rejestracja fiskalna nie powiedzie się.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="234">
          <source>To make this functionality available, you should specify the <bpt id="p1">**</bpt>Skip<ept id="p1">**</ept> and <bpt id="p2">**</bpt>Mark as registered<ept id="p2">**</ept> info codes on a fiscal connector group.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Aby udostępnić tę funkcję, należy określić kody informacji <bpt id="p1">**</bpt>Pomiń<ept id="p1">**</ept> i <bpt id="p2">**</bpt>Oznacz jako zarejestrowane<ept id="p2">**</ept> dla grupy łączników fiskalnych.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="235">
          <source>The information that operators enter is then saved as an info code transaction that is linked to the fiscal transaction.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Informacje wprowadzane przez operatorów są wtedy zapisywane jako transakcja kodu informacji połączona z transakcją fiskalną.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="236">
          <source>For more details about info codes, see <bpt id="p1">[</bpt>Info codes and info code groups<ept id="p1">](../info-codes-retail.md)</ept>.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Aby dowiedzieć się więcej na temat kodów informacji, zobacz <bpt id="p1">[</bpt>Kody informacji i grupy kodów informacji<ept id="p1">](../info-codes-retail.md)</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="237">
          <source>The <bpt id="p1">**</bpt>Product<ept id="p1">**</ept> trigger function isn't supported for the info codes that are used for <bpt id="p2">**</bpt>Skip<ept id="p2">**</ept> and <bpt id="p3">**</bpt>Mark as registered<ept id="p3">**</ept> in fiscal connector groups.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Funkcja wyzwalająca <bpt id="p1">**</bpt>Produkt<ept id="p1">**</ept> nie jest obsługiwana dla kodów informacji, które są używane do obsługi poleceń <bpt id="p2">**</bpt>Pomiń<ept id="p2">**</ept> i <bpt id="p3">**</bpt>Oznacz jako zarejestrowane<ept id="p3">**</ept> w grupach łączników fiskalnych.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="238">
          <source>On the <bpt id="p1">**</bpt>Fiscal connector group<ept id="p1">**</ept> page, on the <bpt id="p2">**</bpt>Info codes<ept id="p2">**</ept> tab, select info codes or info code groups in the <bpt id="p3">**</bpt>Skip<ept id="p3">**</ept> and <bpt id="p4">**</bpt>Mark as registered<ept id="p4">**</ept> fields.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Na stronie <bpt id="p1">**</bpt>Grupa łączników fiskalnych<ept id="p1">**</ept> na karcie <bpt id="p2">**</bpt>Kody informacyjne<ept id="p2">**</ept> wybierz kody informacji lub grupy kodów informacji w polach <bpt id="p3">**</bpt>Pomiń<ept id="p3">**</ept> lub <bpt id="p4">**</bpt>Oznacz jako zarejestrowane<ept id="p4">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="239">
          <source>One fiscal document and one non-fiscal document can be generated on any step of a fiscal registration process.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Jeden dokument fiskalny i jeden dokument niefiskalny mogą być generowane w dowolnym kroku procesu rejestracji fiskalnej.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="240">
          <source>A fiscal document provider extension identifies every type of transaction or event as related to fiscal or non-fiscal documents.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Rozszerzenie dostawcy dokumentów fiskalnych identyfikuje każdy rodzaj transakcji lub zdarzenia w odniesieniu do dokumentów fiskalnych lub niefiskalnych.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="241">
          <source>The error handling feature applies only to fiscal documents.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Funkcja obsługi błędów dotyczy tylko dokumentów fiskalnych.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="242">
          <source><bpt id="p1">**</bpt>Fiscal document<ept id="p1">**</ept> – A mandatory document that should be registered successfully (for example, a fiscal receipt).</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm"><bpt id="p1">**</bpt>Dokument fiskalny<ept id="p1">**</ept> — wymagany dokument, który powinien zostać zarejestrowany pomyślnie (na przykład paragon fiskalny).</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="243">
          <source><bpt id="p1">**</bpt>Non-fiscal document<ept id="p1">**</ept> – A supplementary document for the transaction or event (for example, a gift card slip).</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm"><bpt id="p1">**</bpt>Dokument niefiskalny<ept id="p1">**</ept> — dodatkowy dokument dla transakcji lub zdarzenia (na przykład dokument karty upominkowej).</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="244">
          <source>If the operator must be able to continue to process the current operation (for example, creation or finalization of a transaction) after a health check error occurs, you should enable the <bpt id="p1">**</bpt>Allow skip health check error<ept id="p1">**</ept> permission on the <bpt id="p2">**</bpt>Permission groups<ept id="p2">**</ept> page (<bpt id="p3">**</bpt>Retail <ph id="ph1">\&gt;</ph> Employees <ph id="ph2">\&gt;</ph> Permission groups<ept id="p3">**</ept>).</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Jeśli operator musi mieć możliwość kontynuowania bieżącej operacji (np. tworzenia lub finalizowania transakcji) po wystąpieniu błędu sprawdzania kondycji, należy włączyć uprawnienie <bpt id="p1">**</bpt>Zezwalaj na pominięcie błędu sprawdzania kondycji<ept id="p1">**</ept> na stronie <bpt id="p2">**</bpt>grup uprawnień<ept id="p2">**</ept> (<bpt id="p3">**</bpt>Handel detaliczny <ph id="ph1">\&gt;</ph> Pracownicy <ph id="ph2">\&gt;</ph> Grupy uprawnień<ept id="p3">**</ept>).</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="245">
          <source>For more information about the health check procedure, see <bpt id="p1">[</bpt>Fiscal registration health check<ept id="p1">](fiscal-integration-for-retail-channel.md#fiscal-registration-health-check)</ept>.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Aby uzyskać więcej informacji dotyczących procedury sprawdzania kondycji, zobacz <bpt id="p1">[</bpt>sprawdzanie kondycji rejestracji fiskalnej<ept id="p1">](fiscal-integration-for-retail-channel.md#fiscal-registration-health-check)</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="246">
          <source>Set up fiscal X/Z reports from the POS</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Konfigurowanie raportów fiskalnych X / końcowych raportów sprzedaży z POS</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="247">
          <source>To enable fiscal X/Z reports to be run from the POS, you should add new buttons to a POS layout.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Aby włączyć raporty fiskalne X / końcowe raporty sprzedaży z POS, należy dodać nowe przyciski do układu POS.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="248">
          <source>On the <bpt id="p1">**</bpt>Button grids<ept id="p1">**</ept> page, follow the instructions in <bpt id="p2">[</bpt>Add a custom operation button to the POS layout in Retail headquarters<ept id="p2">](../dev-itpro/add-pos-operations.md#add-a-custom-operation-button-to-the-pos-layout-in-retail-headquarters)</ept> to install the designer and update a POS layout.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Na stronie <bpt id="p1">**</bpt>Siatka przycisków<ept id="p1">**</ept> postępuj zgodnie instrukcjami w <bpt id="p2">[</bpt>Dodawanie przycisków niestandardowych operacji do układu POS w Centrali sieci sprzedaży<ept id="p2">](../dev-itpro/add-pos-operations.md#add-a-custom-operation-button-to-the-pos-layout-in-retail-headquarters)</ept>, aby zainstalować projektanta i zaktualizować układ POS.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="249">
          <source>Select the layout to update.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Wybierz układ do zaktualizowania.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="250">
          <source>Add a new button, and set the <bpt id="p1">**</bpt>Print fiscal X<ept id="p1">**</ept> button property.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Dodaj nowy przycisk i ustaw właściwość przycisku <bpt id="p1">**</bpt>Drukuj częściowy raport obrachunkowy sprzedaży częściowej<ept id="p1">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="251">
          <source>Add a new button, and set the <bpt id="p1">**</bpt>Print fiscal Z<ept id="p1">**</ept> button property.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Dodaj nowy przycisk i ustaw właściwość przycisku <bpt id="p1">**</bpt>Drukuj obrachunkowy końcowy raport sprzedaży<ept id="p1">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="252">
          <source>On the <bpt id="p1">**</bpt>Distribution schedule<ept id="p1">**</ept> page, run the <bpt id="p2">**</bpt>1090<ept id="p2">**</ept> job to transfer changes to the channel database.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Na stronie <bpt id="p1">**</bpt>Harmonogram dystrybucji<ept id="p1">**</ept> uruchom zadanie <bpt id="p2">**</bpt>1090<ept id="p2">**</ept>, aby przenieść zmiany do bazy danych kanału.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="253">
          <source>Enable manual execution of postponed fiscal registration</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Włączanie ręcznego wykonywania odroczonej rejestracji fiskalnej</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="254">
          <source>To enable manual execution of a postponed fiscal registration, you should add a new button to a POS layout.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Aby włączyć ręczne wykonywanie odroczonej rejestracji fiskalnej, należy dodać nowy przycisk do układu punktu sprzedaży.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="255">
          <source>On the <bpt id="p1">**</bpt>Button grids<ept id="p1">**</ept> page, follow the instructions in <bpt id="p2">[</bpt>Add a custom operation button to the POS layout in Retail headquarters<ept id="p2">](../dev-itpro/add-pos-operations.md#add-a-custom-operation-button-to-the-pos-layout-in-retail-headquarters)</ept> to install the designer and update a POS layout.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Na stronie <bpt id="p1">**</bpt>Siatka przycisków<ept id="p1">**</ept> postępuj zgodnie instrukcjami w <bpt id="p2">[</bpt>Dodawanie przycisków niestandardowych operacji do układu POS w Centrali sieci sprzedaży<ept id="p2">](../dev-itpro/add-pos-operations.md#add-a-custom-operation-button-to-the-pos-layout-in-retail-headquarters)</ept>, aby zainstalować projektanta i zaktualizować układ POS.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="256">
          <source>Select the layout to update.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Wybierz układ do zaktualizowania.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="257">
          <source>Add a new button, and set the <bpt id="p1">**</bpt>Complete fiscal registration process<ept id="p1">**</ept> button property.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Dodaj nowy przycisk i ustaw właściwość przycisku <bpt id="p1">**</bpt>Zakończ proces rejestracji fiskalnej<ept id="p1">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="258">
          <source>On the <bpt id="p1">**</bpt>Distribution schedule<ept id="p1">**</ept> page, run the <bpt id="p2">**</bpt>1090<ept id="p2">**</ept> job to transfer your changes to the channel database.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Na stronie <bpt id="p1">**</bpt>Harmonogram dystrybucji<ept id="p1">**</ept> uruchom zadanie <bpt id="p2">**</bpt>1090<ept id="p2">**</ept>, aby przenieść zmiany do bazy danych kanału.</target></trans-unit>
      </group>
    </body>
  </file>
</xliff>