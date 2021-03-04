---
title: Zmiana alokacji rozpoznawania przychodów — scenariusz 1
description: W tym temacie zostanie omówiony scenariusz zmiany alokacji, w ramach którego wprowadzone zostają dwa zamówienia sprzedaży, które są wyłącznie potwierdzane. Wyniki tego scenariusza będą podobne także w przypadku, gdy liczba potwierdzonych zamówień sprzedaży będzie większa niż dwa.
author: kweekley
manager: aolson
ms.date: 12/21/2020
ms.topic: index-page
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: Customer
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2020-12-21
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 2a0add2d4bc01127c1f359736398123a6a3df9fe
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2021
ms.locfileid: "4969659"
---
# <a name="revenue-recognition-reallocation--scenario-1"></a>Zmiana alokacji rozpoznawania przychodów — scenariusz 1

[!include [banner](../includes/banner.md)]

W tym temacie zostanie omówiony scenariusz zmiany alokacji, w ramach którego wprowadzone zostają dwa zamówienia sprzedaży, które są wyłącznie potwierdzane. Wyniki tego scenariusza będą podobne także w przypadku, gdy liczba potwierdzonych zamówień sprzedaży będzie większa niż dwa.

W tym scenariuszu dla opcji **Księgowanie korekt faktury do rozrachunków z odbiorcami** jest wybrana wartość **Nie** na karcie **Rozpoznawanie przychodów** na stronie **Parametry księgi głównej** (**Rozpoznawanie przychodów \> Konfiguracja \> Parametry księgi głównej**).

[![Dla opcji Księgowanie korekt faktury do rozrachunków z odbiorcami jest wybrana wartość Nie](./media/06_rev-rec-scenarios.png)](./media/06_rev-rec-scenarios.png)

Utworzono zamówienie sprzedaży dla odbiorcy US\_SI\_0003. Odbiorca nabywa laptopa (kod towaru S0012) oraz plan pomocy technicznej (kod towaru S0008, „Długotrwała usługa inżynieryjna”) dla laptopa. Przychód z laptopa zostaje natychmiast rozpoznany (przy braku harmonogramu rozpoznawania przychodów). Przychód z planu pomocy technicznej zostanie odroczony i rozpoznany w ciągu 12 miesięcy, zgodnie z zakresem dat określonym w umowie.

[![Wiersze zamówień sprzedaży laptopa oraz planu pomocy technicznej](./media/07_rev-rec-scenarios.png)](./media/07_rev-rec-scenarios.png)

Zamówienie sprzedaży zostaje potwierdzone. Jako że oba towary są skonfigurowane pod kątem alokacji ceny przychodu, cena przychodu jest obliczana po potwierdzeniu zamówienia sprzedaży. Przychód, który zostanie rozpoznany, można sprawdzić na stronie **Alokacja ceny przychodu** (na stronie **Zamówienia sprzedaży**, w okienku akcji, na karcie **Zarządzanie**, w grupie **Rozpoznawanie przychodów** wybierz pozycję **Alokacja ceny przychodu**). Przychód z laptopa w kwocie 1008,01$ zostanie zaksięgowany na koncie przychodów. Przychód z planu pomocy technicznej zostanie zaksięgowany na koncie Przychód odroczony w kwocie 190,99$. Suma cen przychodu musi być równa sumie wierszy skonfigurowanych w celu zarejestrowania alokacji ceny przychodu (1199,00$).

[![Strona alokacji ceny przychodu](./media/08_rev-rec-scenarios.png)](./media/08_rev-rec-scenarios.png)

W momencie sprzedaży klient zdecydował się nie kupować usług instalacyjnych (kod towaru S0001), później zmienił jednak zdanie. W związku z tym dla tego samego odbiorcy zostaje wprowadzone drugie zamówienie sprzedaży.

[![Wiersz zamówienia sprzedaży dotyczący usług instalacyjnych](./media/09_rev-rec-scenarios.png)](./media/09_rev-rec-scenarios.png)

Drugie zamówienie sprzedaży zostaje potwierdzone. Jako że to zamówienie sprzedaży zawiera tylko jeden wiersz, alokacja ceny przychodu nie jest realizowana podczas potwierdzania zamówienia sprzedaży. Alokacja cen przychodów ma miejsce tylko, jeśli istnieją co najmniej dwa unikatowe towary i jeśli towary te zostały skonfigurowane pod kątem alokacji cen przychodów.

Jeśli wspomniane nowe zamówienie sprzedaży stanowi jedyną zmianę wprowadzaną do umowy odbiorcy, można teraz uruchomić proces zmiany alokacji. W jednym z dwóch zamówień sprzedaży wybierz opcję **Zmień alokację ceny za pomocą nowych wierszy zamówienia**, aby otworzyć stronę **Zmień alokację ceny za pomocą nowych wierszy zamówienia**. Możesz również wybrać kolejno **Rozpoznawanie przychodów \> Zadania okresowe \> Zmień alokację ceny za pomocą nowych wierszy zamówienia**. Wybierz dwa zamówienia sprzedaży i odpowiadające im wiersze zamówienia sprzedaży, a następnie wybierz opcję **Aktualizuj zmianę alokacji**. W kolumnie **Kwota po zmianie alokacji** znajduje się nowa cena przychodu dla każdego wiersza zamówienia sprzedaży.

[![Nowe ceny przychodu na stronie Zmień alokację ceny za pomocą nowych wierszy zamówienia](./media/10_rev-rec-scenarios.png)](./media/10_rev-rec-scenarios.png)

W przypadku wybrania opcji **Oczekiwany załącznik** nie są wyświetlane żadne dane; wynika to z faktu, że żadne faktury nie zostały zaksięgowane.

Aby zakończyć proces zmiany alokacji, wybierz opcję **Przetwarzanie**. Nawet jeśli nic nie zostanie zaksięgowane, zostanie wyświetlony monit o podanie daty księgowania. Po zakończeniu procesu zmiany alokacji na stronie **Alokacja ceny przychodu** dla każdego zamówienia sprzedaży będzie wyświetlana alokacja ceny dla wszystkich towarów uwzględnionych na obu zamówieniach sprzedaży. Innymi słowy, strona **Alokacja ceny przychodu** dla każdego zamówienia sprzedaży będzie zawierać towar, który nie istnieje na danym zamówieniu sprzedaży, jako że jest on uwzględniony w ramach tej samej umowy, ale na innym zamówieniu sprzedaży.

> [!TIP]
> Aby dostarczyć kontekst, w jakim są wyświetlane dodatkowe towary, można dodać do siatki inne kolumny, takie jak **Identyfikator zmiany alokacji** i **Zamówienie sprzedaży**.
> 
> [![Dodatkowe kolumny na stronie Alokacje ceny przychodu](./media/11_rev-rec-scenarios.png)](./media/11_rev-rec-scenarios.png)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]