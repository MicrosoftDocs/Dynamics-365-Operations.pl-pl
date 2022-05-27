---
title: FIFO z wartością fizyczną i oznaczeniami
description: Pierwszy na wejściu — pierwszy na wyjściu (First in, first out; FIFO) to model magazynu, w którym wcześniejsze nabycia są wydawane w pierwszej kolejności. Finansowo zaktualizowane elementy z magazynu są rozliczane z pierwszymi finansowo zaktualizowanymi przychodami do magazynu, na podstawie daty finansowej transakcji magazynowej.
author: JennySong-SH
ms.date: 02/02/2022
ms.topic: article
ms.search.form: InventJournalLossProfit, InventMarking, InventModelGroup, SalesTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: 54682
ms.search.region: Global
ms.author: yanansong
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 663dce9f871e96fec7017616732428c49b1224a0
ms.sourcegitcommit: 9166e531ae5773f5bc3bd02501b67331cf216da4
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/03/2022
ms.locfileid: "8676251"
---
# <a name="fifo-with-physical-value-and-marking"></a>FIFO z wartością fizyczną i oznaczeniami

[!include [banner](../includes/banner.md)]


First in, first out (FIFO) to metoda zarządzania zapasami i ich wyceny, w której zapasy, które zostały wyprodukowane lub nabyte jako pierwsze, są sprzedawane, wykorzystywane lub usuwane w pierwszej kolejności. Podczas procesu zamknięcia inwentaryzacji w Microsoft Dynamics 365 Supply Chain Management system tworzy rozrachunki, w których pierwsze przyjęcie jest dopasowywane do pierwszego wydania, i tak dalej.

Rozliczenia i zasada współmierności oparte są na dacie finansowej transakcji inwentaryzacyjnych. Wstępna ocena rozliczeń i korekt może być dokonana poprzez uruchomienie procesu przeliczania inwentarza.

Możesz obejść zasadę FIFO, oznaczając transakcje inwentaryzacyjne tak, by odbiór konkretnej pozycji był rozliczany z konkretnym wydaniem. Okresowe zamknięcie inwentaryzacji jest wymagane, gdy używasz modelu inwentaryzacji FIFO do tworzenia rozrachunków i korygowania wartości wydań zgodnie z zasadą FIFO. Dopóki nie przeprowadzisz procesu zamknięcia inwentarza, transakcje wydania są wyceniane według średniej bieżącej z momentu aktualizacji fizycznej i finansowej. Jeśli nie używasz znakowania, średnia krocząca jest obliczana w momencie przeprowadzania fizycznej lub finansowej aktualizacji. Poniższe przykłady ilustrują wpływ stosowania FIFO w trzech konfiguracjach:

- FIFO bez opcji **Włącz wartość fizyczną**
- FIFO z opcją **Włącz wartość fizyczną**
- FIFO z oznaczaniem

## <a name="fifo-without-the-include-physical-value-option"></a>FIFO bez opcji Włącz wartość fizyczną

W tym przykładzie pole wyboru **Uwzględnij wartość fizyczną** jest wyczyszczony w grupie modeli pozycji dla zwolnionego produktu. Na ilustracji przedstawiono następujące transakcje:

- 1a. Fizyczny przychód magazynowy w ilości 1 i po koszcie 10,00 USD.
- 1b. Finansowy przychód magazynowy w ilości 1 i po koszcie 10,00 USD.
- 2a. Fizyczny przychód magazynowy w ilości 1 i po koszcie 20,00 USD.
- 2b. Finansowy przychód magazynowy w ilości 1 i po koszcie 22,00 USD.
- 3a. Fizyczny rozchód magazynowy w ilości 1 po koszcie własnym 16,00 USD (średnia ruchoma zaksięgowanych finansowo transakcji).
- 3b. Finansowy rozchód magazynowy w ilości 1 po koszcie własnym 16,00 USD (średnia ruchoma zaksięgowanych finansowo transakcji).
- 4a. Fizyczny przychód magazynowy w ilości 1 i po koszcie 25,00 USD.
- 5a. Fizyczny przychód magazynowy w ilości 1 i po koszcie 30,00 USD.
- 5b. Finansowy przychód magazynowy w ilości 1 i po koszcie 30,00 USD.
- 6a. Fizyczny rozchód magazynowy w ilości 1 po koszcie własnym 23,00 USD (średnia ruchoma zaksięgowanych finansowo transakcji)
- 7\. Wykonywane jest zamknięcie magazynu. Zgodnie z metodą FIFO, pierwszy finansowo zaktualizowany rozchód będzie rozliczony z pierwszym finansowo zaktualizowanym przychodem i tak dalej. W tym przykładzie jedno rozliczenie jest tworzone między 1b a 3b. Korekta o ‑6,00 USD zostanie wprowadzona do 3b, a ostateczny koszt wyniesie 10,00 USD.

Nowy średni bieżący koszt własny odzwierciedla średnią finansowo zaktualizowanych transakcji. Poniższe ilustracje pokazują efekty modelu magazynu FIFO na tę serię transakcji, gdy opcja **Włącz wartość fizyczną** nie jest używana.

![FIFO bez opcji Włącz wartość fizyczną.](./media/fifo-without-include-physical-value.png)

**Objaśnienie wykresu**

- Transakcje magazynowe zostały przedstawione w postaci strzałek pionowych.
- Transakcje fizyczne są reprezentowane przez krótsze jasnoszare strzałki.
- Transakcje finansowe są reprezentowane przez dłuższe czarne strzałki.
- Przychody magazynowe zostały przedstawione w postaci strzałek pionowych nad osią czasu.
- Rozchody magazynowe zostały przedstawione w postaci strzałek pionowych pod osią czasu.
- Każda nowa transakcja dotycząca przychodu bądź rozchodu została oznaczona nową etykietą.
- Każda strzałka pionowa jest oznaczona sekwencyjnym identyfikatorem, na przykład *1a*. Identyfikatory te wskazują kolejność księgowań transakcji magazynowych na osi czasu.
- Każda data w diagramie jest oddzielona cienką, czarną, pionową linią. Data jest podana na dole diagramu.
- Każde zamknięcie magazynu zostało przedstawione w postaci czerwonej pionowej linii przerywanej.
- Rozliczenia dokonane przed zamknięciem magazynu zostały przedstawione w postaci linii zakończonych strzałkami, biegnących ukośnie od przychodu do rozchodu.

## <a name="fifo-with-the-include-physical-value-option"></a>FIFO z opcją Włącz wartość fizyczną

Jeśli pole wyboru **Włącz wartość fizyczną** jest zaznaczone dla towaru na stronie **Grupa modeli pozycji**, system używa zarówno fizycznej, jak i finansowej transakcji przyjęcia do obliczenia średniego kroczącego kosztu własnego. W razie potrzeby system dokona również korekt w fizycznie zaktualizowanej transakcji dotyczącej rozchodu. Zamknięcie inwentaryzacji wykorzystujące model inwentaryzacji FIFO dokonuje rozliczeń tylko z transakcjami, które są aktualizowane finansowo. Na ilustracji przedstawiono następujące transakcje:

- 1a. Fizyczny przychód magazynowy w ilości 1 i po koszcie 10,00 USD.
- 1b. Finansowy przychód magazynowy w ilości 1 i po koszcie 10,00 USD.
- 2a. Fizyczny przychód magazynowy w ilości 1 i po koszcie 20,00 USD.
- 2b. Finansowy przychód magazynowy w ilości 1 i po koszcie 22,00 USD.
- 3a. Fizyczne wydanie zapasów w ilości 1 szt. po cenie nabycia 16,00 USD (średnia bieżąca z transakcji zaksięgowanych fizycznie i finansowo).
- 3b. Wydanie finansowe zapasów dla ilości 1 szt. w cenie nabycia 16,00 USD (średnia bieżąca z transakcji zaksięgowanych fizycznie i finansowo).
- 4a. Fizyczny przychód magazynowy w ilości 1 i po koszcie 25,00 USD.
- 5a. Fizyczny przychód magazynowy w ilości 1 i po koszcie 30,00 USD.
- 5b. Finansowy przychód magazynowy w ilości 1 i po koszcie 30,00 USD.
- 6a. Fizyczne wydanie zapasów w ilości 1 szt. po cenie nabycia 23,67 USD (średnia bieżąca z transakcji zaksięgowanych fizycznie i finansowo).
- 7\. Wykonywane jest zamknięcie magazynu. Zgodnie z metodą FIFO, pierwszy finansowo zaktualizowany rozchód będzie rozliczony z pierwszym finansowo zaktualizowanym przychodem i tak dalej. W tym przykładzie jedno rozliczenie jest tworzone między 1b a 3b. Korekta o ‑6,00 USD zostanie wprowadzona do 3b, a ostateczny koszt wyniesie 10,00 USD. Dodatkowo transakcja 6a zostanie skorygowana względem transakcji przyjęcia 2b. System nie rozliczy tych transakcji, ponieważ przyjęcie jest zaktualizowane fizycznie, ale nie finansowo. Zamiast tego, tylko korekta w wysokości -1,67 USD zostanie zaksięgowana do transakcji fizycznej emisji, a wynikowy skorygowany koszt będzie wynosił 22,00 USD.

![FIFO z opcją Włącz wartość fizyczną.](./media/fifo-with-include-physical-value.png)

Zauważ, że wynik uruchomienia procesu zamknięcia inwentaryzacji jest taki sam, niezależnie od tego, czy zaznaczysz opcję **Włącz wartość fizyczną** na stronie **Grupa modelu artykułu**. Opcja **Włącz wartość fizyczną** wpływa tylko na średnią bieżącą.

**Objaśnienie wykresu**

- Transakcje magazynowe zostały przedstawione w postaci strzałek pionowych.
- Transakcje fizyczne są reprezentowane przez krótsze jasnoszare strzałki.
- Transakcje finansowe są reprezentowane przez dłuższe czarne strzałki.
- Przychody magazynowe zostały przedstawione w postaci strzałek pionowych nad osią czasu.
- Rozchody magazynowe zostały przedstawione w postaci strzałek pionowych pod osią czasu.
- Każda nowa transakcja dotycząca przychodu bądź rozchodu została oznaczona nową etykietą.
- Każda strzałka pionowa jest oznaczona sekwencyjnym identyfikatorem, na przykład *1a*. Identyfikatory te wskazują kolejność księgowań transakcji magazynowych na osi czasu.
- Każda data w diagramie jest oddzielona cienką, czarną, pionową linią. Data jest podana na dole diagramu.
- Każde zamknięcie magazynu zostało przedstawione w postaci czerwonej pionowej linii przerywanej.
- Rozliczenia dokonane przed zamknięciem magazynu zostały przedstawione w postaci linii zakończonych strzałkami, biegnących ukośnie od przychodu do rozchodu.

## <a name="fifo-with-marking"></a>FIFO z oznaczaniem

Oznaczanie to proces, który pozwala połączyć (oznaczyć) transakcję wydania z transakcją przyjęcia. Może to mieć miejsce zarówno przed, jak i po zaksięgowaniu transakcji. Procesu tego można użyć po to, aby sprawdzić dokładny koszt zapasów w momencie księgowania transakcji lub zamknięcia magazynu.

Na przykład dział obsługi klienta zaakceptował pilne zamówienie od ważnego odbiorcy. Ponieważ zamówienie jest pilne, trzeba zapłacić więcej za ten towar, aby spełnić wymagania odbiorcy. Trzeba się upewnić, że koszt tej pozycji magazynowej zostanie uwzględniony w marży (lub koszcie własnym sprzedaży, COGS) na tej fakturze za zamówienie sprzedaży. Po zaksięgowaniu zamówienia zakupu zapasy zostaną przyjęte do magazynu po koszcie 120 USD. Jeśli to zamówienie sprzedaży zostanie przypisane do takiego zamówienia zakupu przed zaksięgowaniem dokumentu dostawy lub faktury, koszt sprzedanych towarów wyniesie 120 USD (nie będzie bieżącą średnią ruchomą kosztów towaru). Jeśli dotyczące zamówienia sprzedaży dokument dostawy lub faktura zostaną zaksięgowane przed wspomnianym przypisaniem, wówczas kosztem sprzedanych towarów będzie średnia ruchoma kosztów własnych. Przed zamknięciem magazynu obie powyższe transakcje mogą nadal zostać przypisane do siebie.

Jeśli transakcja przyjęcia jest oznaczona do transakcji wydania, metoda wyceny określona w grupie modeli towaru jest ignorowana, a system dokonuje wzajemnego rozliczenia tych transakcji. Możesz ręcznie zaznaczyć transakcję przeciwko wierszowi zamówienia sprzedaży na stronie **Szczegóły zamówienia sprzedaży**, wybierając **Zapasy \> Oznaczenie** na skróconej karcie **Wiersze zamówienia sprzedaży**. Można wyświetlić otwarte transakcje przychodu na stronie **Zaznaczanie**. Można dopasować lub oznaczyć transakcję rozchodu dla otwartej transakcji przychodu dla indywidualnej pozycji z zaksięgowanego arkusza korekt zapasów. Na ilustracji przedstawiono następujące transakcje:

- 1a. Fizyczny przychód magazynowy w ilości 1 i po koszcie 10,00 USD.
- 1b. Finansowy przychód magazynowy w ilości 1 i po koszcie 10,00 USD.
- 2a. Fizyczny przychód magazynowy w ilości 1 i po koszcie 20,00 USD.
- 2b. Finansowy przychód magazynowy w ilości 1 i po koszcie 22,00 USD.
- 3a. Fizyczny rozchód magazynowy w ilości 1 po koszcie własnym 16,00 USD (średnia ruchoma zaksięgowanych finansowo transakcji).
- 3b. Finansowy rozchód magazynowy w ilości 1 po koszcie własnym 16,00 USD (średnia ruchoma zaksięgowanych finansowo transakcji).
- 3c. Inwentaryzacyjna emisja finansowa dla 3b jest oznaczona jako inwentaryzacyjna emisja finansowa dla 2b.
- 4a. Fizyczny przychód magazynowy w ilości 1 i po koszcie 25,00 USD.
- 5a. Fizyczny przychód magazynowy w ilości 1 i po koszcie 30,00 USD.
- 5b. Finansowy przychód magazynowy w ilości 1 i po koszcie 30,00 USD.
- 6a. Fizyczny rozchód magazynowy w ilości 1 po koszcie własnym 23,00 USD (średnia ruchoma zaksięgowanych finansowo transakcji)
- 7\. Wykonywane jest zamknięcie magazynu. W oparciu o zasadę oznaczania, która wykorzystuje metodę FIFO, oznaczone transakcje są rozliczane między sobą. W tym przykładzie, 3b jest rozliczane z 2b, a korekta o 6,00 USD jest księgowana na 3b, aby wartość wynosiła 22,00 USD. W tym przykładzie nie są dokonywane żadne dodatkowe rozliczenia, ponieważ zamknięcie tworzy rozliczenia tylko dla transakcji zaktualizowanych finansowo.

Poniższa ilustracja pokazuje wpływ modelu magazynowego FIFO na tę serię transakcji, jeśli używane są oznaczenia między przychodem i rozchodem.

![FIFO z oznaczaniem.](./media/fifo-with-marking.png)

**Objaśnienie wykresu**

- Transakcje magazynowe zostały przedstawione w postaci strzałek pionowych.
- Transakcje fizyczne są reprezentowane przez krótsze jasnoszare strzałki.
- Transakcje finansowe są reprezentowane przez dłuższe czarne strzałki.
- Przychody magazynowe zostały przedstawione w postaci strzałek pionowych nad osią czasu.
- Rozchody magazynowe zostały przedstawione w postaci strzałek pionowych pod osią czasu.
- Każda nowa transakcja dotycząca przychodu bądź rozchodu została oznaczona nową etykietą.
- Każda strzałka pionowa jest oznaczona sekwencyjnym identyfikatorem, na przykład *1a*. Identyfikatory te wskazują kolejność księgowań transakcji magazynowych na osi czasu.
- Każda data w diagramie jest oddzielona cienką, czarną, pionową linią. Data jest podana na dole diagramu.
- Każde zamknięcie magazynu zostało przedstawione w postaci czerwonej pionowej linii przerywanej.
- Rozliczenia i oznaczenia dokonane przed zamknięciem magazynu zostały przedstawione w postaci linii zakończonych strzałkami, biegnących ukośnie od przychodu do rozchodu.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
