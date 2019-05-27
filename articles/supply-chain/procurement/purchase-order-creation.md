---
title: Tworzenie zamówień zakupu
description: W tym artykule opisano proces i opcje ręcznego tworzenia zamówienia zakupu.
author: FrankDahl
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PurchTable
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 93053
ms.assetid: 25b1c9f1-20f8-4cf5-b87c-876e32f68846
ms.search.region: Global
ms.author: fdahl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: cb703ff7419a59aa174e16d8d988a96814e4fec6
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/15/2019
ms.locfileid: "1572680"
---
# <a name="create-purchase-orders"></a>Tworzenie zamówień zakupu

[!include [banner](../includes/banner.md)]

[!include [retail name](../includes/retail-name.md)]

W tym artykule opisano proces i opcje ręcznego tworzenia zamówienia zakupu.

Podczas tworzenia zamówienia zakupu ogólne informacje dotyczące całego zamówienia są podane w nagłówku zamówienia zakupu, a użytkownik dodaje jeden lub więcej wierszy zamówienia zakupu. W tym artykule opisano niektóre najczęściej używane dostępne opcje.  

Zamówienia zakupu można również tworzyć przez kopiowanie wierszy z innego dokumentu zamówienia zakupu lub z zamówienia sprzedaży. W takim przypadku można zmienić znak w zapasach, tak jak zmienia się znak na fakturze, aby wskazać uznanie.  

Chociaż można ręcznie tworzyć zamówienia zakupu, zazwyczaj są one generowane z innych procesów. Zamówienia mogą być tworzone automatycznie na podstawie innych dokumentów, takich jak zapotrzebowania. Alternatywnie mogą być tworzone w ramach procesu planowania głównego przy użyciu mechanizmu zaplanowanych zamówień zakupu. Jeśli używasz umów zakupu, zamówienia zakupu mogą być tworzone przez operację **Zwolnij zamówienie**. Istnieją również bardziej zaawansowane metody automatycznego tworzenia zamówień zakupu. Na przykład można tworzyć zamówienia, gdy są używane dostawy bezpośrednie lub łańcuchy zamówień międzyfirmowych.

## <a name="creating-a-purchase-order-header"></a>Tworzenie nagłówka zamówienia zakupu
Podczas tworzenia nowego zamówienia zakupu zostanie wyświetlone okno dialogowe, gdzie można wprowadzić najbardziej typowe informacje nagłówka zamówienia zakupu. Po kliknięciu przycisku **OK** w celu zamknięcia okna dialogowego zamówienie zostanie utworzone i można wtedy określić dodatkowe informacje w nagłówku.  

Pierwszym szczegółem, który należy rozważyć podczas tworzenia zamówienia zakupu, jest typ zamówienia. Najczęściej jest używany typ **Zamówienie zakupu**. Jednakże jeśli jest wymagana faktura korygująca, można użyć typu **Zwrot towaru**.  

Musisz określić dostawcę w polu **Konto dostawcy**. W tym polu można szukać według konta lub nazwy dostawcy. Jeśli dostawca dostarcza z wielu lokalizacji, ale używa jednego konta płatnika, można wybrać do konto płatnika w polu **Konto płatnika**, a następnie używać go z różnymi kontami dostawcy. Jeśli zachodzi potrzeba utworzenia zamówienia zakupu dla produktów, które nie będzie zamawiane wielokrotnie, można użyć opcji **Dostawca jednorazowy**. Ta opcja automatycznie tworzy nowe konto dostawcy, które jest oznaczone jako konto jednorazowe, aby umożliwić późniejszy proces czyszczenia kont jednorazowych w module **Rozrachunki z dostawcami**. Po wybraniu konta dostawcy wiele pól w nagłówku zamówienia zakupu dziedziczy wartości domyślne z informacji skojarzonych z kontem dostawcy. Na przykład domyślny oddział i magazyn dostawy są kopiowane z informacji o dostawcy. Jednak można zastąpić te domyślne wartości, jeśli zakup jest przeznaczony dla innej lokalizacji.  

Jeśli dostawca podał numer referencyjny zamówienia, można zapisać tę informację w polu **Odwołanie do dostawcy**. Dla zamówień, których towary są zwracane, należy określić wartość w polu **RMA**, aby utworzyć odwołanie do autoryzacji dostawcy na przetwarzanie zwrotu.  

Jeśli z zamówieniem jest skojarzona umowa zakupu, należy podać tę informację w polu **Umowa zakupu**.  

Nagłówek zamówienia zakupu zawiera także informacje dotyczące opłat mających zastosowanie do całego zamówienia, a nie pojedynczych wierszy. Opłaty mogą być automatycznie dodawane do zamówienia, jeśli skonfigurowano automatyczne opłaty dla dostawcy lub grupy opłat dostawcy. Można także ręcznie dodać opłaty do nagłówka zamówienia, w okienku akcji klikając przycisk **Obsługuj opłaty**.

## <a name="adding-purchase-order-lines"></a>Dodawanie wierszy zamówienia zakupu
Zamówienia zakupu mogą dotyczyć fizycznych produktów lub usług. Ustawienie w grupie modeli zapasów określa, czy konkretny numer pozycji stosuje się do produktu czy usługi. Zazwyczaj kupowany towar jest określany przez numer towaru (pozycji). Jednak jeśli zamówienie opiewa na produkty lub usługi, które podlegają bezpośredniemu zużyciu, pozycję można określić również za pomocą kategorii zaopatrzenia.  

Wiersze zamówienia zakupu zawierają wiele pól, ale wiele z nich ma wartości domyślne lub dziedziczone z nagłówka zamówienia. Dodatkowe pola są ustawiane po wybraniu produktu lub usługi. Pola najczęściej ustawiane ręcznie to m.in. pola numeru pozycji, ilości i żądanej daty dostawy. Informacje o cenie jednostkowej i rabatach również są bardzo ważne, ale wartości tych pól są często określane przez umowy handlowe lub umowy zakupu.  

Podczas wybierania produktu można szukać według całości lub części nazwy produktu zamiast według numeru towaru. Jeżeli produkt ma kilka wariantów, np. różne rozmiary, można wyświetlić przegląd dostępnych wariantów, używając do tego funkcji **Dodaj wiersze** lub funkcji wyszukiwania dostępnej w polu **Numer wariantu**.  

Często trzeba określić kilka wymiarów dla towarów wybranych w każdym wierszu zamówienia zakupu. Wymiary, które muszą zostać określone, zależą od grup wymiarów przypisanych do definicji produktu głównego. Na przykład często trzeba określić oddział i magazyn, aby wskazać lokalizację, do której należy dostarczyć produkt. W celu określenia wariantów produktu podajesz numer wariantu albo wprowadzasz wartości jednego lub więcej wymiarów produktu, np. koloru, rozmiaru, konfiguracji lub stylu. Wymiary śledzenia, np. partia i numer seryjny, umożliwiają jednoznaczną identyfikację każdej partii zapasów. Po utworzeniu zamówienia można przechwycić istniejące w nim wartości wymiarów, używając do tego operacji **Rejestracja**. Na przykład zamówiono ilość pięciu sztuk towaru. Później rejestrujesz, że trzy z tych sztuk będą czarne, a dwie niebieskie. Ta metoda jest alternatywą dla przechwytywanie informacji o wymiarach podczas rejestracji przyjęcia.  

Można sprawdzać szczegóły stanu transakcji magazynowej dla produktów magazynowanych. Na przykład można chcieć sprawdzić dostępne zapasy, aby określić, ile trzeba zamówić. Alternatywnie można przejrzeć stan zapasów zamówionej ilości, aby zobaczyć, czy doszło do rejestracji przychodzącego przyjęcia.  

Wiersz zamówienia zakupu używany w celu zwrotu produktu do dostawcy będzie miał wartość ujemną. Można wybrać konkretną partię do zwrotu za pomocą operacji **Rezerwacja**.  

Czasami trzeba podzielić zamówioną ilość, tak aby różne części zostały dostarczone w różnych dniach. Można skonfigurować te dostawy za pomocą akcji **Harmonogram dostaw**, która jest dostępna w menu **Wiersz zamówienia zakupu** menu w widoku **Wiersze**.  

Opłaty mogą być automatycznie dodawane do wierszy zamówienia zakupu, jeśli skonfigurowano automatyczne opłaty dla dostawcy lub grupy opłat dostawcy oraz dla pozycji lub grupy opłat za pozycje. Jednak najczęściej opłaty są dodawane ręcznie na poziomie wiersza zamówienia. Aby dodać opłatę, otwórz stronę **Obsługuj opłaty** za pomocą działania **Obsługuj opłaty** w menu **Finanse** w widoku **Wiersze**. Zaletą dodawania opłat bezpośrednio na poziomie wiersza zamówienia jest to, że opłatę można przydzielić jako koszt zapasów. Aby skonfigurować kody opłat w celu ujęcia kosztu produktu, należy użyć **Pozycja** po stronie debetowej (obciążeniowej). Tego rodzaju opłaty muszą być przydzielone z nagłówka zamówienia zakupu do wierszy, aby można było potwierdzić zamówienie. Na przykład można chcieć przydzielić opłaty na podstawie ilości w każdym wierszu. Kategoria opłat wpływa również na sposób ujmowania opłat. Na przykład opłaty stałe określają stałą kwotę, a opłaty Procentowe są obliczane jako procent kwoty netto w wierszu zamówienia. Zamówienia zakupu mogą być przypisane do ładunku, a ładunek może zawierać preliminarz oczekiwanych wydatków z tytułu kosztów transportu. Wydatek ten można przydzielić z powrotem od ładunku do wierszy zamówienia zakupu.

## <a name="purchase-order-actions"></a>Akcje związane z zamówieniem zakupu
Po dodaniu nagłówka i wierszy do zamówienia zakupu często należy wykonać dodatkowe kroki, zanim zamówienie będzie gotowe do potwierdzenia. Ponieważ jest dostępnych bardzo dużo opcji, warto użyć funkcji [Wyszukiwanie akcji](../../fin-and-ops/get-started/action-search.md), aby znaleźć odpowiednią pozycję menu.  

Produkty w zamówieniu można konfigurować w taki sposób, aby zawierały pozycje dodatkowe. Pozycje dodatkowe to produkty, które muszą lub mogą zostać kupione razem z innymi produktami. Pozycje dodatkowe mogą być dodawane bezpłatnie jako produkty towarzyszące lub też można decydować, czy mają być dodawane do zamówienia, czy nie. Pozycje dodatkowe można przejrzeć po każdym dodanym wierszu zamówienia. Jednakże prawdopodobnie bardziej wygodne będzie przejrzeć i dodać odpowiednie pozycje dodatkowe razem dla wszystkich wierszy zamówienia za pomocą strony **Pozycje dodatkowe**, którą można otworzyć z okienka akcji.  

Rabaty są zwykle dodawane do tworzonych wierszy. Jednak niektóre rabaty dotyczą całego zamówienia:

-   Operacja **Rabat końcowy** oblicza łączny procent rabatu stosowany do kompletnego zamówienia. Nie należy mylić tego rabatu z procentem rabatu gotówkowego. Rabaty gotówkowe są stosowane w momencie zapłaty faktury i zależą od uregulowania płatności w określonym terminie.
-   Jeśli jest stosowany rabat obejmujący wiele wierszy, należy użyć działania **Rabat wspólny** w celu obliczenia i przypisania rabatu do zamówienia. Rabaty wspólne to rabaty, które mogą być oferowane, gdy miks produktów w zamówieniu przekracza próg wspólny. Tego typu rabaty stosuje tylko kilka firm.

Opłaty mające kod opłaty wykorzystujący typ obciążenia **Pozycja** muszą być przypisane na poziomie wiersza, aby można było potwierdzić zamówienie. Wygodne może się okazać przypisanie tych opłat na poziomie nagłówka zamówienia, co pozwoli określić łączną kwotę opłaty. Jednak w takim przypadku opłata musi następnie zostać przydzielona na niższy poziom do każdego wiersza, zanim zamówienie będzie można potwierdzić. W celu podzielenia kwot z opłat, które są przypisane na poziomie nagłówka, w dół do wierszy zamówienia można użyć operacji **Alokacja opłat**. Opłaty można podzielić według kwoty netto każdego wiersza, według zamówionej ilości lub równomiernie między wiersze zamówienia. Po przydzieleniu opłat do wierszy opłata jest usuwana z nagłówka zamówienia.  

Zamówienia zakupu można skonfigurować tak, aby środki budżetu zostały przydzielone do zamówienia, zanim mogą być przetwarzane. W takim przypadku można przydzielić budżet za pomocą akcji **Sprawdzanie budżetu**.  

Może wystąpić konieczność opóźnienia finalizacji zamówienia zakupu. Na przykład mogą być potrzebne dodatkowe informacje o produktach lub usługach lub może zajść potrzeba uzyskania autoryzacji na wydatek. Istnieje kilka sposobów wstrzymania zamówienia. Na przykład można poczekać z potwierdzeniem zamówienia. Alternatywnie, jeśli jest stosowany przepływ pracy zarządzania zmianami, nie przesyłaj zamówienia do zatwierdzenia. Jeśli należy zablokować wszystkie zamówienia dla konkretnego dostawcy, można również oznaczyć dostawcę w jego danych głównych jako **Wstrzymane** w zakresie przetwarzania. Istnieją okoliczności, które mogą uniemożliwić przetwarzanie zamówienia. Na przykład przetwarzanie może być niemożliwe, jeśli przekroczono limity kredytowe lub jeżeli wymagane środki budżetowe nie są dostępne.

<a name="additional-resources"></a>Dodatkowe zasoby
--------

[Omówienie zamówień zakupu](purchase-order-overview.md)

[Zatwierdzanie i potwierdzanie zamówienia zakupu](purchase-order-approval-confirmation.md)

[Przyjęcie produktów względem zamówień zakupu](product-receipt-against-purchase-orders.md)

[Omówienie faktur od dostawców](../../financials/accounts-payable/vendor-invoices-overview.md)



