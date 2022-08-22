---
title: Lista funkcji modułu ER w kategorii funkcji specyficznych dla domeny biznesowej
description: Ten artykuł zawiera ogólne informacje o funkcjach specyficznych dla domeny biznesowej obsługiwanych w module Raportowanie elektroniczne (ER).
author: kfend
ms.date: 12/12/2019
ms.prod: ''
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: kfend
ms.search.region: Global
ms.author: filatovm
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
ms.openlocfilehash: b1ac46cf10d57b40af1fa99021156ad97a17ba20
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/12/2022
ms.locfileid: "9272691"
---
# <a name="list-of-er-functions-in-the-business-domainspecific-category"></a>Lista funkcji modułu ER w kategorii funkcji specyficznych dla domeny biznesowej

[!include [banner](../includes/banner.md)]

Funkcje specyficzne dla domeny w module raportowania elektronicznego (ER) mogą służyć do wykonywania obliczeń i żądań dostępu do danych, które są specyficzne dla implementacji aplikacji Microsoft Dynamics 365 Finance. Ten artykuł zawiera podsumowanie tych funkcji.

## <a name="list-of-supported-functions"></a>Lista obsługiwanych funkcji

| Funkcja| Opis |
|---------|-------------|
| [CH_Bank_Mod_10](er-functions-other-chbankmode10.md) | Ta funkcja zwraca wartość *Ciąg*, która reprezentuje odwołanie do wierzyciela jako wyrażenie MOD10, na podstawie cyfr określonego numeru faktury. |
| [CN_GBT_AdditionalDimensionID](er-functions-other-cngbtadditionaldimensionid.md) | Ta funkcja zwraca wartość typu *Ciąg*, która reprezentuje identyfikator pojedynczego wymiaru finansowego pobrany z określonego ciągu. Określony ciąg przedstawia wszystkie wymiary jako rozdzielaną przecinkami listę identyfikatorów. |
| [ConvertCurrency](er-functions-other-convertcurrency.md) | Ta funkcja zwraca wartość *rzeczywistą*, która reprezentuje wynik konwertowania określonej kwoty pieniężnej ze wskazanej waluty źródłowej na określoną walutę docelową przy użyciu ustawień określonej firmy na określony dzień. |
| [CurCredRef](er-functions-other-curcredref.md) | Ta funkcja zwraca wartość *Ciąg*, która reprezentuje odwołanie do wierzyciela na podstawie cyfr określonego numeru faktury. |
| [FA_Balance](er-functions-other-fabalance.md) | Ta funkcja zwraca wartość *Kontener (rekord)*, która składa się z danych dla salda składnika majątku dla określonego elementu składnika majątku, kodu modelu ewidencji, roku sprawozdawczego i daty raportowania. |
| [FA_Sum](er-functions-other-fasum.md) | Ta funkcja zwraca wartość *Kontener (rekord)*, która składa się z danych dla kwot składnika majątku dla określonego elementu składnika majątku, kodu modelu ewidencji i zakresu dat. |
| [GetCurrentCompany](er-functions-other-getcurrentcompany.md) | Ta funkcja zwraca wartość *Ciąg* reprezentującą kod firmy (jednostki prawnej), do której użytkownik jest aktualnie zalogowany. |
| [ISOCredRef](er-functions-other-isocredref.md) | Ta funkcja zwraca wartość *Ciąg*, która reprezentuje odwołanie do wierzyciela w formacie Międzynarodowej Organizacji Normalizacyjnej (ISO) w oparciu o cyfry i znaki alfabetyczne określonego numeru faktury. |
| [IsValidCharacterISO7064](er-functions-other-isvalidchariso7064.md) | Ta funkcja zwraca wartość *logiczną* **TRUE**, jeśli podany ciąg tekstowy reprezentuje prawidłowy międzynarodowy numer konta bankowego (IBAN). W przeciwnym wypadku zwraca ona wartość *logiczną* **FALSE**. |
| [Mod_97](er-functions-other-mod97.md) | Ta funkcja zwraca wartość *Ciąg*, która reprezentuje odwołanie do wierzyciela jako wyrażenie MOD97, na podstawie cyfr określonego numeru faktury. |
| [NumSeqValue](er-functions-other-numseqvalue.md) | Ta funkcja zwraca wartość typu *Ciąg*, która reprezentuje nową wygenerowaną wartość sekwencji numerów na podstawie określonej sekwencji numerów, zakresu i identyfikatora zakresu. Identyfikator zakresu jest równy kodowi firmy podawanemu przez kontekst, w którym jest uruchamiany format ER. |
| [RoundAmount](er-functions-other-roundamount.md) | Ta funkcja zwraca wartość *rzeczywistą* reprezentującą wynik zaokrąglania określonej ilości do określonej liczby miejsc dziesiętnych zgodnie z określoną regułą zaokrąglania. |
| [TableName2ID](er-functions-other-tablename2id.md) | Ta funkcja zwraca numeryczną reprezentację identyfikatora tabeli dla określonej nazwy tabeli jako wartość typu *Liczba całkowita*. |

## <a name="additional-resources"></a>Dodatkowe zasoby

[Raportowanie elektroniczne — omówienie](general-electronic-reporting.md)

[Projektant formuł w module Raportowanie elektroniczne](general-electronic-reporting-formula-designer.md)

[Język formuł raportowania elektronicznego](er-formula-language.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
