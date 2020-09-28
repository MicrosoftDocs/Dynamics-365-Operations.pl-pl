---
title: Typ miejsca docelowego raportowania elektronicznego (ER)
description: Ten temat zawiera informacje dotyczące konfigurowania lokalizacji docelowej e-mail dla poszczególnych składników FOLDER lub FILE formatu sprawozdawczości elektronicznej (ER) skonfigurowanych do generowania dokumentów wychodzących.
author: NickSelin
manager: AnnBe
ms.date: 01/27/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: DocuType, ERSolutionTable, ERFormatDestinationTable
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
ms.openlocfilehash: 72f67ad915ba2acc90ecb52bdb97e42504450a03
ms.sourcegitcommit: 445f6d8d0df9f2cbac97e85e3ec3ed8b7d18d3a2
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/01/2020
ms.locfileid: "3745568"
---
# <a name="email-destination"></a>Pocztowe miejsce docelowe

[!include [banner](../includes/banner.md)]

Możesz konfigurować lokalizacje docelową e-mail dla poszczególnych składników FOLDER lub FILE formatu sprawozdawczości elektronicznej (ER) skonfigurowanych do generowania dokumentów wychodzących. Na podstawie ustawienia lokalizacji docelowej wygenerowany dokument jest dostarczony jako załącznik do rekordu listy zadań ER.

W ustawieniu **Włączone** zaznacz wartość **Tak**, aby wysłać plik wyjściowy pocztą e-mail. Po włączeniu tej opcji można określić adresatów wiadomości e-mail oraz edytować jej temat i treść. Można zdefiniować stałe teksty tematu i treści wiadomości e-mail lub używać [formuł](er-formula-language.md) ER w celu dynamicznego tworzenia tekstów wiadomości e-mail. 

Adresy e-mail dla modułu ER można konfigurować na dwa sposoby. Konfigurację można wykonać w taki sam sposób, aby funkcja zarządzania drukowaniem kończyła się lub można było rozpoznać adres e-mail za pomocą bezpośredniego odwołania do konfiguracji ER, korzystając z formuły.

[![Uruchom miejsce docelowe e-mail](./media/ER_Destinations-EnableSingleDestination.png)](./media/ER_Destinations-EnableSingleDestination.png)

## <a name="email-address-types"></a>Typy adresów e-mail

Po kliknięciu przycisku **Edytuj** dla pola **Do** lub **DW** pojawi się okno dialogowe **Wiadomość e-mail do**. Następnie można wybrać typ adresu e-mail, który ma być używany. Typy **Wiadomości e-mail konfiguracji** oraz **Zarządzanie drukowaniem** są obecnie obsługiwane.

[![Wybierz typ wiadomości e-mail](./media/ER_Destinations-EmailSelectAddressType.png)](./media/ER_Destinations-EmailSelectAddressType.png)

### <a name="print-management"></a>Zarządzanie drukowaniem

Jeśli wybierzesz typ wiadomości e-mail w opcji **Zarządzania drukowaniem**, można wprowadzić stałe adresy e-mail w polu **Do**. 

[![Konfigurowanie stałych adresów e-mail](./media/ER_Destinations-EmailFixedAddress.png)](./media/ER_Destinations-EmailFixedAddress.png)

Aby używać adresów e-mail, które nie są stałe, należy wybrać typ źródła wiadomości e-mail dla plikowego miejsca docelowego. Obsługiwane są następujące wartości: **Odbiorca**, **Dostawca**, **Prospekt**, **Kontakt**, **Konkurent**, **Pracownik**, **Kandydat**, **Potencjalny dostawca** i **Niezatwierdzony dostawca**. Po wybraniu typu źródła wiadomości e-mail użyj przycisku obok pola **Konto źródłowe poczty e-mail**, aby otworzyć formularz **Projektant formuł**. Ten formularz umożliwia dołączenie formuły, która zwraca się w czasie wykonywania, **konta strony** wybranego typu źródła z przetworzonego dokumentu do miejsca docelowego poczty e-mail.

[![Konfiguruj konto źródłowe poczty e-mail](./media/ER_Destinations-EmailDefineAddressSource.png)](./media/ER_Destinations-EmailDefineAddressSource.png)

Formuły są specyficzne dla konfiguracji ER. W polu **Formuła** wprowadź specyficzne dla dokumentu odwołanie do podmiotu typu Odbiorca lub Dostawca. Zamiast wpisywać informacje ręcznie, można odszukać węzeł źródła danych reprezentujący konto odbiorcy lub dostawcy, a następnie wybrać przycisk **Dodaj źródło danych**, aby zaktualizować formułę. Na przykład jeśli używasz konfiguracji **przelewu bankowego ISO 20022**, węzłem reprezentującym konto dostawcy jest `'\$PaymentsForCoveringLetter'.Creditor.Identification.SourceID`.

Jeśli wprowadzisz wartość ciągu, na przykład `"DE-001"`, i zapiszesz formułę, wiadomość zostanie wysłana do osoby kontaktowej dla dostawcy **DE-001**.


[![Strona projektanta formuł ER](./media/ER_Destinations-EmailDefineAddressSourceFormula.png)](./media/ER_Destinations-EmailDefineAddressSourceFormula.png)

[![Konfiguruj konto źródłowe atrybutów poczty e-mail](./media/ER_Destinations-EmailDefineAddressSourceAttributes.png)](./media/ER_Destinations-EmailDefineAddressSourceAttributes.png)



### <a name="configuration-email"></a>Adres e-mail konfiguracji

Użyj tego typu wiadomości e-mail, jeśli używana konfiguracja ma w źródłach danych węzeł zwracający **adres e-mail**. W projektancie formuł można użyć źródeł danych i funkcji, aby uzyskać poprawnie sformatowany adres e-mail. Na przykład jeśli używasz konfiguracji **przelewu bankowego ISO 20022**, węzłem reprezentującym adres e-mail osoby kontaktowej dostawcy jest `'$PaymentsForCoveringLetter'.Creditor.ContactDetails.Email`.

[![Konfiguruj adres źródłowy poczty e-mail](./media/ER_Destinations-EmailDefineAddressSource2.png)](./media/ER_Destinations-EmailDefineAddressSource2.png)

## <a name="additional-resources"></a>Dodatkowe zasoby

- [Omówienie raportowania elektronicznego (ER)](general-electronic-reporting.md)
- [Miejsca docelowe raportowania elektronicznego (ER)](electronic-reporting-destinations.md)
- [Projektant formuł w module Raportowanie elektroniczne (ER)](general-electronic-reporting-formula-designer.md)
