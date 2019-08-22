---
title: Konfigurowanie i generowanie plików płatności dodatnich
description: W tym temacie wyjaśniono, jak konfigurować płatności dodatnie i generować pliki płatności dodatnich.
author: abruer
manager: AnnBe
ms.date: 03/06/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BankPositivePayFormat
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 88433
ms.assetid: 73f3dcf6-040a-44ad-9512-7b3e0d17a571
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
ms.openlocfilehash: 00ab2b28813dce4f5317fc93c13c89d0753d4033
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/01/2019
ms.locfileid: "1837187"
---
# <a name="set-up-and-generate-positive-pay-files"></a>Konfigurowanie i generowanie plików płatności dodatnich

[!include [banner](../includes/banner.md)]

W tym temacie wyjaśniono, jak konfigurować płatności dodatnie i generować pliki płatności dodatnich. 

Konfigurowanie płatności dodatnich w celu generowania elektronicznej listy czeków dostarczanych do banku. Gdy czek zostanie przekazany do banku, bank porównuje go z listą czeków. Jeśli czek pasuje do czeku na liście, wówczas bank rozlicza czek. Jeśli czek nie pasuje do czeku na liście, bank wstrzymuje czek w celu sprawdzenia.

## <a name="security-for-positive-pay-files"></a>Zabezpieczenia plików płatności dodatnich
Pliki płatności dodatnich mogą zawierać poufne informacje na temat odbiorców płatności i kwot czeków. W związku z tym musisz podjąć odpowiednie środki bezpieczeństwa od momentu wygenerowania plików aż do ich odbioru przez bank. Pliki płatności dodatnich są pobierane do lokalizacji określonej przez przeglądarkę internetową. Ponieważ pliki płatności dodatnich mogą zawierać informacje poufne, ważne jest, aby tylko upoważnieni użytkownicy mieli dostęp umożliwiający generowanie i wyświetlanie tych informacji w programie Microsoft Dynamics 365 for Finance and Operations. Poniższa tabela pomaga określić uprawnienia, które są wymagane.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Zadanie</th>
<th>Uprawnienie</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Generowanie plików płatności dodatnich ze strony listy <strong>Konta bankowe</strong> lub strony <strong>Konta bankowe</strong>.</td>
<td><ul>
<li><strong>Obsługa informacji o bankowych płatnościach dodatnich</strong> (BankPositivePayProcess)</li>
<li><strong>BankPositivePayExportEntityView</strong> (BankPositivePayExportEntityView)</li>
</ul></td>
</tr>
<tr class="even">
<td>Generowanie plików płatności dodatnich dla wielu firm i kont bankowych ze strony <strong>Generuj plik płatności dodatnich</strong>.</td>
<td><ul>
<li><strong>Obsługa informacji o bankowych płatnościach dodatnich</strong> (BankPositivePayProcess)</li>
<li><strong>BankPositivePayExportEntityView</strong> (BankPositivePayExportEntityView)</li>
</ul></td>
</tr>
<tr class="odd">
<td>Wyświetlanie plików płatności dodatnich na stronie <strong>Podsumowanie pliku płatności dodatnich</strong>.</td>
<td><strong>Wyświetl informacje o bankowych płatnościach dodatnich wielu firm</strong> (BankPositivePayView)</td>
</tr>
<tr class="even">
<td>Potwierdzanie pliku płatności dodatnich na stronie <strong>Podsumowanie pliku płatności dodatnich</strong>.</td>
<td><strong>Potwierdź plik płatności dodatnich</strong> (BankPositivePayConfirm)</td>
</tr>
<tr class="odd">
<td>Wycofywanie pliku płatności dodatnich na stronie <strong>Podsumowanie pliku płatności dodatnich</strong>.</td>
<td><strong>Odwołaj plik płatności dodatnich</strong> (BankPositivePayRecall)</td>
</tr>
</tbody>
</table>

## <a name="set-up-a-positive-pay-format"></a>Konfigurowanie formatu płatności dodatnich
Pliki płatności dodatnich tworzy się za pomocą jednostek danych. Zanim będzie można wygenerować plik płatności dodatnich, należy zdefiniować format danych wejściowych przekształcenia, który będzie używany do translacji danych czeku na format umożliwiający komunikację z bankiem. Na stronie **Format płatności dodatnich** można utworzyć identyfikator i opis formatu pliku. Format danych wejściowych przekształcenia musi być typu XML Konkretny format zależy od używanego pliku przekształcenia. Na przykład dołączony testowy plik XSLT (Extensible Stylesheet Language Transformations) używa formatu **XML-Element**. Użyj akcji **Przekaż plik używany na potrzeby przekształcenia**, aby określić lokalizację pliku przekształcenia dla formatu wymaganego przez bank.

## <a name="example-xslt-file-for-positive-pay-file"></a>Przykład: Plik płatności dodatnich typu XSLT
    <xsl:stylesheet version="1.0" xmlns:xsl="http://www.w3.org/1999/XSL/Transform" xmlns:msxsl="urn:schemas-microsoft-com:xslt" exclude-result-prefixes="msxsl xslthelper" xmlns="urn:iso:std:iso:20022:tech:xsd:pain.001.001.02" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xslthelper="http://schemas.microsoft.com/BizTalk/2003/xslthelper">
      <xsl:output method="xml" omit-xml-declaration="no" version="1.0" encoding="utf-8"/>
      <xsl:template match="/">
        <xsl:value-of select="'
    '" />
        <Document>
          <xsl:value-of select="'
    '" />
          <!--Header Begin-->
          <xsl:value-of select='string("Vendor ID,Vendor Name,Voided,Document Type,Check Date,Check Number,Check Amount,Checkbook ID,Vendor Class ID,Posted Date")'/>
          <xsl:value-of select="'
    '" />
          <!--Header End-->
          <xsl:for-each select="Document/BANKPOSITIVEPAYEXPORTENTITY">
            <!--Cheque Detail begin-->
            <xsl:value-of select='RECIPIENTACCOUNTNUM/text()'/>
            <xsl:value-of select="','" />
            <xsl:value-of select='BANKNEGINSTRECIPIENTNAME/text()'/>
            <xsl:value-of select="','" />
            <xsl:choose>
              <xsl:when test='CHEQUESTATUS/text()=normalize-space("Void") or CHEQUESTATUS/text()=normalize-space("Rejected") or CHEQUESTATUS/text()=normalize-space("Cancelled")'>
                <xsl:value-of select='string("Yes")'/>
              </xsl:when>
              <xsl:when test='CHEQUESTATUS/text()=normalize-space("Payment")'>
                <xsl:value-of select='string("No")'/>
              </xsl:when>
              <xsl:otherwise>
                <xsl:value-of select='string(" ")'/>
              </xsl:otherwise>
            </xsl:choose>
            <xsl:value-of select="','" />
            <xsl:value-of select='string("Payment")'/>
            <xsl:value-of select="','" />
            <xsl:value-of select='TRANSDATE/text()'/>
            <xsl:value-of select="','" />
            <xsl:value-of select='CHEQUENUM/text()'/>
            <xsl:value-of select="','" />
            <xsl:value-of select='AMOUNTCUR/text()'/>
            <xsl:value-of select="','" />
            <xsl:value-of select='string("BOA-#1812")'/>
            <xsl:value-of select="','" />
            <xsl:choose>
              <xsl:when test='RECIPIENTTYPE/text()=normalize-space("Vend")'>
                <xsl:value-of select='VENDGROUP/text()'/>
              </xsl:when>
              <xsl:otherwise>
                <xsl:value-of select='CUSTGROUP/text()'/>
              </xsl:otherwise>
            </xsl:choose>
            <xsl:value-of select="','" />
            <xsl:value-of select='TRANSDATE/text()'/>
            <xsl:value-of select="'
    '" />
          </xsl:for-each>
        </Document>
      </xsl:template>
    </xsl:stylesheet>

## <a name="assign-the-positive-pay-format-to-a-bank-account"></a>Przypisywanie formatu płatności dodatnich do konta bankowego
Dla każdego konta bankowego, dla którego chcesz wygenerować informacje o płatnościach dodatnich, należy przypisać format płatności dodatnich, który został określony w poprzedniej sekcji. Na stronie **Konta bankowe** zaznacz format płatności dodatnich odpowiadający kontu bankowemu. W polu **Data początkowa płatności dodatnich** wprowadź pierwszą datę dla generowania plików płatności dodatnich. Wypełnienie tego pola jest bardzo ważne. W przeciwnym razie pierwszy generowany plik płatności dodatnich będzie obejmował wszystkie czeki, które zostały utworzone dla tego konta bankowego.

## <a name="assign-a-number-sequence-for-positive-pay-files"></a>Konfigurowanie sekwencji identyfikatorów plików płatności dodatnich
Każdy plik płatności dodatnich musi mieć unikatowy numer. Na karcie **Sekwencje identyfikatorów** na stronie **Parametry modułu Zarządzanie gotówką i bankami** utwórz sekwencję identyfikatorów plików płatności dodatnich.

## <a name="generate-a-positive-pay-file-for-a-single-bank-account"></a>Generowanie pliku płatności dodatnich dla jednego konta bankowego
Można wygenerować plik płatności dodatnich dla pojedynczej firmy i pojedynczego konta bankowego. Informacje o generowaniu plików płatności dodatnich dla wielu firm i kont bankowych w tym samym czasie znajdują się w następnej sekcji. Aby wygenerować plik płatności dodatnich dla jednej firmy i jednego konta bankowego, ze strony **Konta bankowe** otwórz okno dialogowe **Generuj plik płatności dodatnich**. W polu **Data graniczna** wprowadź ostatnią datę czeku do uwzględnienia w pliku płatności dodatnich. Wszystkie czeki, które jeszcze nie zostały uwzględnione w pliku płatności dodatnich do tej daty czeku, znajdą się w pliku.

## <a name="generate-a-positive-pay-file-for-multiple-bank-accounts"></a>Generowanie pliku płatności dodatnich dla wielu kont bankowych
Aby wygenerować plik płatności dodatnich dla wielu kont bankowych, użyj zadania okresowego **Generuj plik płatności dodatnich**. Wybierz format pliku płatności dodatnich oraz określ, czy wygenerować plik dla wszystkich firm, czy tylko dla wybranej firmy. Można również wygenerować plik płatności dodatnich dla wszystkich kont bankowych używających określonego formatu płatności dodatnich albo tylko dla wybranego konta bankowego. W polu **Data graniczna** wprowadź ostatnią datę czeku do uwzględnienia w pliku płatności dodatnich. Wszystkie czeki, które jeszcze nie zostały uwzględnione w pliku płatności dodatnich do tej daty czeku, znajdą się w pliku.

## <a name="view-the-results-of-positive-pay-file-generation"></a>Wyświetlanie wyników generowania pliku płatności dodatnich
Po wygenerowaniu pliku płatności dodatnich wyniki można obejrzeć na stronie **Podsumowanie pliku płatności dodatnich**. Aby wyświetlić szczegółowe informacje o poszczególnych czekach, należy użyć strony szczegółów **Plik płatności dodatnich**.

## <a name="confirm-a-positive-pay-file"></a>Potwierdź plik płatności dodatnich
Po zapłaceniu czeków wymienionych w pliku płatności dodatnich, otrzymasz numer potwierdzenia z banku. Wtedy można potwierdzić plik płatności dodatnich. Na stronie **Podsumowanie pliku płatności dodatnich** zaznacz plik płatności dodatnich, który ma stan **Utworzone**, a następnie wybierz akcję **Wprowadź potwierdzenie**. Po potwierdzeniu pliku płatności dodatnich następuje odnotowanie numeru potwierdzenia otrzymanego z banku.

## <a name="recall-a-positive-pay-file"></a>Odwoływanie pliku płatności dodatnich
Jeśli trzeba zmodyfikować plik płatności dodatnich, można go wycofać. Na stronie **Podsumowanie pliku płatności dodatnich** zaznacz plik płatności dodatnich, który ma stan **Utworzone**, a następnie wybierz akcję **Wycofaj**. Dla każdego czeku w pliku płatności dodatnich jest resetowane pole wskazujące, czy czek jest uwzględniony w pliku płatności dodatnich. Następnie można utworzyć nowy plik płatności dodatnich zawierający wycofany czek.



