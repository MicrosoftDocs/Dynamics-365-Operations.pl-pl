---
title: Integracja środków trwałych
description: Środki trwałe mogą być zintegrowane z modułami Księga główna, Zarządzanie zapasami, Rozrachunki z odbiorcami i Rozrachunki z dostawcami. Istnieje również możliwość takiego skonfigurowania modułu Środki trwałe, aby był on zintegrowany z zamówieniami zakupu.
author: moaamer
ms.date: 03/05/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AssetTable
audience: Application User
ms.reviewer: kfend
ms.custom: 3501
ms.assetid: f0639053-d99c-432a-8ead-5c26e0d4eaec
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: dea14735031f6a97772d1a00ad274fdfd3defb17
ms.sourcegitcommit: e09f5c6d78d7942af950ae3f6407df2fedceeba4
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/06/2022
ms.locfileid: "8719895"
---
# <a name="fixed-assets-integration"></a>Integracja środków trwałych

[!include [banner](../includes/banner.md)]

Środki trwałe mogą być zintegrowane z modułami Księga główna, Zarządzanie zapasami, Rozrachunki z odbiorcami i Rozrachunki z dostawcami. Istnieje również możliwość takiego skonfigurowania modułu Środki trwałe, aby był on zintegrowany z zamówieniami zakupu.

## <a name="general-ledger"></a>Księga główna

W księdze głównej wartość wszystkich środków trwałych jest zwykle sumowana na kilku kontach głównych, które są wymagane do sprawozdawczości finansowej. Jednak na stronie **Środki trwałe** można utworzyć wiele rekordów środków trwałych. Te rekordy mogą zawierać informacje, takie jak cena nabycia, amortyzacja i szacowanie. Każdorazowo podczas księgowania transakcji dla środków trwałych aktualizowane są konta główne. Konta główne dla środków trwałych zawsze pokazują zaktualizowaną wartość środków trwałych.

Na stronie **Profile księgowania środków trwałych** należy określić konta główne, na których będą księgowane transakcje księgi środków trwałych. Należy także określić typy transakcji środków trwałych, które są księgowane na każdym koncie głównym. Użytkownik może tworzyć różne kombinacje kont głównych dla środków trwałych w zależności od ilości szczegółów dotyczących środków trwałych, które mają znaleźć się w księdze głównej. Konta główne mogą bazować na typach transakcji, księgach i innych kontach głównych.

## <a name="inventory-management"></a>Zarządzanie zapasami
W arkuszu magazynowym środków trwałych można wprowadzić nabycie środków trwałych, które firma wyprodukowała lub skonstruowała dla siebie. Następnie można przenieść towary magazynowe do środków trwałych jako nabycie lub część nabycia. 

Środki trwałe można również nabywać za pomocą zamówień zakupu. Jeśli zamówienia zakupu zawierają pozycje magazynowe określone jako środki trwałe, wartość opcji **Zezwalaj na nabywanie środków trwałych z zakupów** na stronie **Parametry środków trwałych** określa, czy nabycie środka trwałego jest księgowane w momencie księgowania faktury. Jeden wiersz zakupu spowoduje utworzenie jednego środka trwałego, niezależnie od ilości. Wpływ nabycia środków trwałych na magazyn zależy od konfiguracji firmy. 

Gdy pozycja magazynowa staje się nabyciem środków trwałych za pośrednictwem arkusza magazynowego, zamówienia zakupu lub propozycji nabycia, jest tworzona transakcja nabycia do księgi środków trwałych. Jeśli nabycie do księgi obejmuje księgę pochodną, jest również tworzona transakcja nabycia do księgi pochodnej. 

O zmniejszeniu zapasów w momencie zaksięgowania nabycia decydują reguły księgowania skonfigurowane na stronie **Księgowanie** w module Zarządzanie zapasami. Jednak zapasy nie zawsze są zmniejszane w momencie zaksięgowania faktur związanych ze środkami trwałymi. W niektórych przypadkach mogą być nabywane środki trwałe do użytku wewnętrznego, jak na przykład komputer przenośny dla działu sprzedaży. Podczas pracy z zamówieniami zakupu można używać zarówno towarów skonfigurowanych do odsprzedaży, jak i do użytku wewnętrznego. 

Jeśli dla środków trwałych w pewnych grupach towarów są używane określone konta przychodu i rozchodu, tego samego towaru magazynowego można używać zarówno dla zakupów wewnętrznych, jak i dla zapasów do odsprzedaży. 

Środki trwałe przeznaczone do użytku wewnętrznego są skonfigurowane tak, aby miały typ konta **Przychód środków trwałych**. Ten typ konta jest używany do śledzenia przyjęcia środków trwałych. Po zaksięgowaniu faktury dostawcy, należy użyć konta przychodów środka trwałego, jeśli jest spełniony jeden z następujących warunków:

-   Wiersz faktury zawiera istniejący środek trwały do celów wewnętrznych.
-   Pole wyboru **Nowy środek trwały?** jest zaznaczone dla wiersza dokumentu przyjęcia produktów, który został zaksięgowany.
-   Pole wyboru **Utwórz nowy środek trwały** jest zaznaczone w wierszu faktury od dostawcy.

Zazwyczaj to konto jest kontem wydatków. Typ konta **Przychód środków trwałych** można skonfigurować dla grupy towarów lub dla pojedynczego towaru na karcie **Zamówienie zakupu** na stronie **Grupa pozycji** lub **Księgowanie** page.

Podobnie środki trwałe, które są przeznaczone do użytku wewnętrznego, mogą być ustawione tak, aby miały typ konta **Rozchód środków trwałych**. Ten typ konta jest używany do śledzenia wydawania środków trwałych nabywcy. Gdy dokonane zostaje nabycie środka przy użyciu polecenia zakupu, konto rozchodu środków trwałych służy jako konto przeciwstawne do konta debetowego. Nabycie składnika aktywów może być księgowane w momencie księgowania faktury dostawcy lub księgowania nabycia składnika w arkuszu Środków trwałych, zazwyczaj za pomocą propozycji nabycia. Typ konta **Rozchód środków trwałych** można skonfigurować dla grupy towarów lub dla pojedynczego towaru na karcie **Zapasy** na stronie **Grupa pozycji** lub **Księgowanie pozycji**. 

Ostatecznie konta główne, które są używane do księgowania są ustalane na podstawie opcji określonych dla grupy modeli towaru dla integracji z księgą. Ponadto konta główne, które są używane mogą się różnić w zależności od tego, czy środek trwały jest przypisany do wiersza zamówienia zakupu. Konta są wybierane z profili księgowania dla poszczególnych grup towarów. 
**Uwaga:** Jeśli podczas księgowania przyjęć produktów istnieje rezerwacja zapasów, nie można przypisać środka trwałego do wiersza ani utworzyć go na podstawie wiersza. 

Konta, na których są księgowane transakcje środków trwałych, zależą od dwóch czynników: czy środki są kupowane czy konstruowane w firmie oraz od typu transakcji dla danego środka. 

Typ transakcji łączy transakcję magazynową z profilem księgowania w module Środki trwałe. Ponieważ profil księgowania w module Środki trwałe określa, które konta zostaną zaktualizowane, wybór typu transakcji środków trwałych pośrednio oznacza również wybór kont głównych, na których zostanie zaksięgowana transakcja. W przypadku skonstruowanych i nabytych środków trwałych typem transakcji jest zazwyczaj **Nabycie** lub **Korekta nabycia**.

## <a name="accounts-receivable"></a>Rozrachunki z odbiorcami
Integracja środków trwałych z modułu Rozrachunki z odbiorcami stosuje profile księgowania, które są ustawiane w środach trwałych. Te profile księgowania są uaktywniane, gdy środek trwały, księga i typ transakcji na środkach trwałych są zaznaczone do faktury dla odbiorcy przed zaksięgowaniem faktury dla odbiorcy. Ponieważ środki trwałe nie są częścią zarządzania zapasami, należy użyć strony **Faktura niezależna** po sprzedaniu środka trwałego. 

Jeżeli księga zawiera księgę pochodną, po zaksięgowaniu faktury dla odbiorcy zostanie utworzona transakcja w księdze pochodnej.

## <a name="accounts-payable"></a>Rozrachunki z dostawcami
Środki trwałe są zwykle nabywane od dostawców zewnętrznych. Strony **Parametry środków trwałych** można użyć w celu określenia, czy nabycia środków trwałych mają być zawsze księgowane w momencie księgowania faktur od dostawcy, czy tylko w module Środki trwałe. W przypadku zezwolenia na księgowanie w module Rozrachunki z dostawcami konta środków trwałych są aktualizowane zawsze po zaksięgowaniu faktury od dostawcy dotyczącej nabycia środka trwałego. 

W przypadku skonfigurowania opcji księgowania nabycia środka trwałego w momencie księgowania faktury transakcja jest księgowana zgodnie z profilami księgowania określonymi w module Środki trwałe dla różnych typów transakcji środków trwałych. Sposób zaksięgowania zależy od środka trwałego, księgi i typu transakcji na środkach trwałych wybranych na stronie **Zamówienie zakupu** przed zaksięgowaniem faktury od dostawcy. 

Jeżeli księga zawiera księgę pochodną, po zaksięgowaniu faktury od dostawcy zostanie utworzona transakcja w księdze pochodnej.

Integracja dla każdego wiersza zamówienia jest uaktywniana na karcie **Środki trwałe** na skróconej karcie **Szczegóły wiersza** na stronie **Zamówienie zakupu**. Zamówienie zakupu dla środków trwałych można wysłać do dostawcy. Jednak konta główne i środki trwałe są aktualizowane dopiero po zaksięgowaniu faktury dostawcy po odebraniu środków trwałych. Ponieważ zamówienia zakupu mogą zawierać tylko towary magazynowe, nabycie środków trwałych wpływa na zapasy zgodnie z konfiguracją firmy.

## <a name="project-management-and-accounting"></a>Zarządzanie projektami i ich księgowanie
Projekt można skojarzyć ze środkiem trwałym, na który ten projekt ma wpływ. Ponadto poszczególne fazy, zadania lub podprojekty można skojarzyć z innymi środkami trwałymi. Jeden środek trwały można skojarzyć z każdym rekordem projektu. Skojarzenie można utworzyć w momencie wprowadzania numeru środka trwałego w polu **Numer środka trwałego** na stronie **Projekty**. Typem projektu musi być **Wewnętrzny** lub **Projekt kosztów**. 

Można również użyć strony **Projekty** w celu wyświetlenia szczegółów dotyczących składników aktywów skojarzonych z projektami. Aby wyświetlić rekord środka trwałego, na skróconej karcie **Ustawienia** kliknij łącze tego składnika, co spowoduje otwarcie strony **Środki trwałe**. Potem kliknij kolejno opcje **Projekty** &gt; **Wszystkie projekty**, aby wyświetlić projekty skojarzone ze środkiem trwałym. 

Zazwyczaj środki trwałe kojarzy się z projektami, gdy projekty są związane z pracą, konserwacją lub udoskonalaniem środka trwałego. Po ukończeniu projektu nie jest tworzone automatycznie żadne zwiększenie wartości środka trwałego. W związku z tym jeśli jest wymagane zwiększenie wartości, należy je utworzyć ręcznie. 

Aby usunąć skojarzenie między projektem a środkiem trwałym, wyczyść pole **Numer środka trwałego** na stronie **Projekty**. 

Istnieje również możliwość oznaczenia tworzonego lub produkowanego środka trwałego jako elementu projektu szacowania. Na zakończenie projektu szacowanego można automatycznie zaksięgować transakcję nabycia środka trwałego.

Aby uzyskać więcej informacji, zobacz [Nabywanie środków trwałych za pomocą zaopatrzenia](acquire-assets-procurement.md)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]
