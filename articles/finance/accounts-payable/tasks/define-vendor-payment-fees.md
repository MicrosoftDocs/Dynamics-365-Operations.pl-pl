---
title: Definiowanie opłat od płatności dostawcy
description: Skonfiguruj opłaty od płatności dla dostawcy.
author: abruer
ms.date: 02/11/2022
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: VendPaymFee, VendPaymModeFee, BankAccountTableLookUp
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: c490bb4d15fa03742b12f337046f26976ab70d29
ms.sourcegitcommit: 3105642fca2392edef574b60b4748a82cda0a386
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/12/2022
ms.locfileid: "8109838"
---
# <a name="define-vendor-payment-fees"></a>Definiowanie opłat od płatności dostawcy

[!include [banner](../../includes/banner.md)]

Skonfiguruj opłaty od płatności dla dostawcy. W zadaniu wykorzystano firmę demonstracyjną USMF.

1. Wybierz kolejno opcje **Rozrachunki z dostawcami > Ustawienia płatności > Opłata**.
2. Kliknij przycisk **Nowy**.
3. W polu **Identyfikator opłaty** wpisz wartość.
    * **Identyfikator opłaty** powinien wskazywać, kiedy opłata będzie używana, np. „Opłata_EFT”.  
4. W polu **Nazwa** wpisz wartość.
5. W polu **Opis opłaty** wpisz wartość.
    * Dodaj opis, który bardziej szczegółowo wyjaśnia, kiedy opłata jest naliczana.  
6. W polu **Opłata** zaznacz opcję **Dostawca** lub **Księga**.
    * Jeśli opłaty będą zaliczane w koszty firmy, jest używana opcja **Księga**. Opcja **Dostawca** jest używany, jeśli opłata będzie naliczana dla dostawcy.  
7. Wprowadź konto główne, na którym opłata będzie naliczane w ciężar kosztów.
    * Ta opcja jest dostępna tylko wtedy, gdy w polu **Opłata** wybrano opcję **Księga**.  
8. Wybierz arkusz, w którym można używać tej opłaty. 
    * W przypadku opłaty od płatności dostawcy należy wybrać arkusz „Wypłaty dla dostawców”.  
9. Kliknij przycisk **Zapisz**.
10. Kliknij **Ustawienia opłat płatności**.
    * Przejdź do okna **Ustawienia opłat** i wskaż, kiedy opłata ma być domyślnie stosowana do wybranego arkusza.  
11. Wybierz opcję **Tabela**, **Grupa** lub **Wszystko**.
    * Opcja **Tabela** służy do wybierania jednego konta bankowego, opcja **Grupa** służy do wybierania grupy bankowej, a opcja **Wszystko** powoduje używanie tej konfiguracji opłat dla wszystkich kont bankowych.  
12. Zaznacz grupę bankową lub konto bankowe.
    * Wyszukiwanie spowoduje wyświetlenie grupy bankowej, jeśli została wybrana opcja **Grupa**, a kont bankowych, jeśli wybrano opcję **Tabela**.  
13. Zaznacz metodę płatności, w której opłata będzie naliczana.
14. Wybierz **specyfikację płatności** dla wybranej metody płatności.
    * **Specyfikacja płatności** jest używana do płatności za pomocą przelewów elektronicznych.  
15. Określ, czy opłata będzie procentem, kwotą czy interwałem.
16. Wprowadź procent lub kwotę opłaty.
    * Jeśli w polu **Opłata** zaznaczono opcję Wartość procentowa, wprowadź wartość procentową. Jeśli w polu **Opłata** zaznaczono opcję Kwota, wprowadź kwotę opłaty. Jeśli w polu **Opłata** zaznaczono opcję **Interwał**, na karcie Interwał zdefiniuj opłaty warstwowe.  
17. W polu **Waluta opłaty** wybierz walutę, w jakiej będzie naliczana opłata.
    * Ta waluta dotyczy opłaty. Waluta płatności jest używana do zdefiniowania, kiedy reguła opłat powinna być stosowana na podstawie waluty płatności. Na przykład bank może nakładać opłatę podczas dokonywania płatności w euro, podczas gdy płatności w innych walutach nie są obciążane.  
18. Kliknij przycisk **Zapisz**.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
