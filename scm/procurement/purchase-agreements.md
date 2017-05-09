---
title: Umowy zakupu
description: "Ten artykuł zawiera informacje o umowach zakupu. Umowa zakupu jest to kontraktem, który zobowiązuje organizację do zakupu określonej ilości lub za określoną kwotę przy użyciu wielu zamówień zakupu na przestrzeni czasu. W zamian za to zobowiązanie kupujący otrzymuje specjalne ceny i rabaty."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: AgreementClassification, AgreementLine, AgreementLinePrompt, PurchAgreement, PurchAgreementCreate, PurchAgreementGenerateReleaseOrder, PurchAgreementHistory, PurchAgreementInvoiceJournal
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 11634
ms.assetid: 8ac20adf-7412-4929-be8c-aaedf23a76ad
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 3d02a15387231160f5b8a237aa11008b91ef1223
ms.openlocfilehash: 3f96d12960e90bb05497d1bc2900d4477551c091
ms.lasthandoff: 03/31/2017


---

# <a name="purchase-agreements"></a>Umowy zakupu

[!include[banner](../includes/banner.md)]


Ten artykuł zawiera informacje o umowach zakupu. Umowa zakupu jest to kontraktem, który zobowiązuje organizację do zakupu określonej ilości lub za określoną kwotę przy użyciu wielu zamówień zakupu na przestrzeni czasu. W zamian za to zobowiązanie kupujący otrzymuje specjalne ceny i rabaty. 

Umowa zakupu może dotyczyć określonej ilości produktu, określonej kwoty produktów w walucie lub określonej kwoty produktów w walucie w kategorii zaopatrzenia. Ceny i rabaty dla umowy zakupu zastępują ceny i rabaty, które są określone w jakichkolwiek istniejących umowach handlowych.  

Na stronie **Umowa zakupu** można tworzyć, stosować i kontynuować działania dotyczące umów zakupu, które istnieją między organizacją użytkownika i dostawcami. Na przykład po utworzeniu umowy zakupu można zamówić bezpośrednio z niej. Każda umowa zakupu ma okres ważności zdefiniowany przez osobę, która tworzy umowę zakupu. Data dostawy zakupu musi się mieścić w datach w okresie obowiązywania.  

Po utworzeniu umowy zakupu należy ją aktywować, aby zaczęła obowiązywać. Aby aktywować umowę zakupu, należy ustawić opcję **Oznaczenie umowy jako obowiązującej** na **Tak**.

## <a name="commitment-types"></a>Typy zobowiązania
Każdy wiersz umowy zakupu jest zobowiązaniem do zakupu czegoś. Do wypełniania zobowiązania można używać wierszy z wielu zamówień zakupu. Istnieją cztery typy zobowiązań:

-   **Zobowiązanie co do ilości produktu** – Zakup określonej ilości produktu.
-   **Zobowiązanie co do wartości produktu** – Zakup produktu za określoną kwotę w walucie.
-   **Zobowiązanie co do wartości w ramach kategorii produktu** – Zakup produktu za określoną kwotę w walucie w kategorii zaopatrzenia. Kwota może dotyczyć towaru z katalogu lub towaru spoza katalogu.
-   **Zobowiązanie co do wartości** – Zakup jakiegokolwiek produktu lub produktów za określoną kwotę w walucie lub w każdej kategorii zaopatrzenia.

## <a name="pricing-terms-for-purchase-agreements"></a>Warunki cenowe umów zakupu
Warunki cenowe mogą się różnić w zależności od typu zobowiązania. Warunki cenowe z umów zakupu zastępują wszelkie inne warunki cenowe skonfigurowane dla umów handlowych. W poniższej tabeli opisano pola związane z cenami, na które ma wpływ każdy typ zobowiązania. Pola zawierające **tak** można zaktualizować w wierszu zamówienia.

| Typ zobowiązania                   | Cena jednostkowa | Jednostka cenowa | Procent rabatu | Kwota rabatu gotówkowego |
|-----------------------------------|------------|------------|------------------|----------------------|
| Zobowiązanie co do ilości produktu       | Tak        | Tak        | Tak              | Tak                  |
| Zobowiązanie co do wartości produktu          |            |            | Tak              |                      |
| Zobowiązanie co do wartości w ramach kategorii produktu |            |            | Tak              |                      |
| Zobowiązanie co do wartości                  |            |            | Tak              |                      |

## <a name="policies-for-purchase-agreements"></a>Zasady dotyczące umowy zakupu
Następujące zasady mają wpływ na sposób działania łącza między zobowiązaniem umowy zakupu i odpowiadającymi mu wierszami zamówienia zakupu:

-   **Wymuszono maks** — Łączna ilość lub kwota dla wszystkich wierszy zamówienia nie może przekraczać ilości lub kwoty określonej w powiązanym zobowiązaniu.
-   **Cena i rabat są stałe** — Cena w wierszu zamówienia i cena na powiązanym zobowiązaniu nie mogą się różnić. Jeśli w wierszu zamówienia zostanie zmieniona cena, łącze do zobowiązania zostanie przerwane. Jeśli łącze do zobowiązania zostanie przerwane, wiersz zamówienia nie będzie brał udziału w wypełnieniu zobowiązania.
-   **Kwota minimalna zwolnienia i Kwota maksymalna zwolnienia** – Jeśli kwota jest określona, wyświetlany jest komunikat po wprowadzeniu zmian do wiersza zamówienia, które powodują, że wiersz zamówienia jest inny niż zobowiązanie powiązane.

## <a name="fulfillment-calculations-for-purchase-agreements"></a>Obliczenia realizacji umów zakupu
Ilości i kwoty realizacji widać na karcie **Realizacja** na skróconej karcie **Szczegóły wiersza** na stronie **Umowa zakupu**.  

Obszar **Realizacja** pokazuje pozostałą kwotę lub ilość, która jest wymagana do wypełnienia zobowiązania.  

Obszar **Umowa** pokazuje ilość całkowitą lub łączną kwotę, na jaką została zawarta umowa sprzedaży.  

Dostępne są wiersze zamówienia zakupu i wiersze faktury wpływające na obliczenia realizacji; aby je wyświetlić, trzeba zaznaczyć działanie **Informacje pokrewne** w wierszach lub w nagłówku umowy zakupu.

## <a name="confirmations-and-version-history-for-purchase-agreements"></a>Potwierdenia i historia wersji umów zakupu
Gdy potwierdzono umowę zakupu, bieżąca wersja umowy zakupu jest przechowywana w tabeli historii. Jeśli zmieni się umowę zakupu, można potwierdzić ją ponownie, aby zachować inną wersję umowy zakupu w historii. Jeśli nie można potwierdzisz umowy zakupu, nadal możesz jej używać do tworzenia zamówień zakupu, ale informacje o historii dla tej umowy nie są zapisywane. Można wyświetlić podgląd lub wydrukować wersje umowy. Następnie można udostępnić zmiany dostawcy w celu uzyskania zatwierdzenia.

## <a name="applying-purchase-agreements-in-the-ordering-process"></a>Stosowanie umów zakupu w procesie zamawiania
Podczas tworzenia zamówienia zakupu można zastosować do niego umowę zakupu. Informacje z postanowień umowy, takie jak warunki płatności, warunki dostawy i adres dostawy, są następnie kopiowane do nagłówka zamówienia zakupu. Jeśli zamówienie zakupu zawiera jeden lub więcej wierszy dla produktów lub kategorii, które są objęte umową, dla tych wierszy są używane ceny i rabaty z umowy zakupu. Kwota lub ilość w wierszu zamówienia przyczynia się do realizacji zobowiązania wynikającego z umowy zakupu. To samo zamówienie zakupu może zawierać zarówno wiersze, które nie są powiązane z umową zakupu, jak i wiersze, które mają zobowiązania dla umowy zakupu.  

Umowę zakupu można wybrać tylko przy tworzeniu zamówienia zakupu. Po utworzeniu zamówienia zakupu nie można wybrać umowy zakupu.  
W niektórych sytuacjach, gdy zamówienia zakupu są tworzone bezpośrednio, można kontrolować, czy program Microsoft Dynamics 365 for Operations automatycznie wyszukuje umowy zakupu. Na przykład można to zrobić podczas automatycznego akceptowania planowanych zamówień zakupu lub tworzenia zamówień zakupu, które są oparte na zamówieniach sprzedaży.

## <a name="purchase-agreements-and-intercompany-trade"></a>Umowy zakupu i handel międzyfirmowy
Można utworzyć międzyfirmowe relacje handlowe między kontami dostawcy i kontami odbiorcy, które znajdują się w różnych firmach. Podczas tworzenia zamówienia sprzedaży lub zamówienia zakupu dla jednej ze stron, tworzy się łańcuch zamówień międzyfirmowych. W łańcuchu zamówień zamówienie sprzedaży i zamówienie zakupu są tworzone w odpowiednich firmach.  

Można utworzyć umowę zakupu lub umowę sprzedaży dla jednej ze stron handlu międzyfirmowego. Można następnie wygenerować odpowiednią umowę sprzedaży lub umowę zakupu dla innej strony transakcji międzyfirmowej w innej firmie.  

Po utworzeniu międzyfirmowego zamówienia zakupu korzystającego z umowy zakupu międzyfirmowego w jednej firmie odpowiadające międzyfirmowe zamówienie sprzedaży korzysta z odpowiedniej międzyfirmowej umowy sprzedaży w innej firmie. Realizacja zobowiązań umowy sprzedaży i realizacja umów zakupu są zsynchronizowane, podobnie jak są synchronizowane z międzyfirmowe zamówienia zakupu i międzyfirmowe zamówienia sprzedaży.

## <a name="financial-dimensions-on-purchase-agreements"></a>Wymiary finansowe umów zakupu
Wymiary finansowe można skopiować do nagłówków dokumentu lub pojedynczych wierszy umowy zakupu. Jeśli zmienisz wymiary w nagłówku umowy lub w wierszu umowy, zmiana nie ma wpływu na jakiekolwiek zwolnione zlecenia, ale zostanie uwzględniona w nowych zamówieniach.

<a name="see-also"></a>Informacje dodatkowe
--------

[Tworzenie umowy zakupu (przewodnik po zadaniu)](https://ax.help.dynamics.com/en/wiki/create-a-purchase-agreement/)

[Tworzenie zlecenia wydania zakupu na podstawie umowy zakupu (przewodnik po zadaniu)](https://ax.help.dynamics.com/en/wiki/create-a-purchase-release-order-from-a-purchase-agreement/)




