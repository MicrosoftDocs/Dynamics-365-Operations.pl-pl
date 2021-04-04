---
title: Importowanie załączników za pomocą jednostki Arkusz finansowy
description: Ten temat zawiera porady dotyczące importowania danych do arkusza finansowego przy użyciu jednostki Arkusz finansowy.
author: rcarlson
manager: AnnBe
ms.date: 04/20/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: sericks
ms.custom: 94363
ms.assetid: 0b8149b5-32c5-4518-9ebd-09c9fd7f4cfc
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: adc5ad88b7b58c67154b340f4125b0b89a0cf4d6
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/09/2021
ms.locfileid: "5566904"
---
# <a name="importing-vouchers-by-using-the-general-journal-entity"></a>Importowanie załączników za pomocą jednostki Arkusz finansowy

[!include [banner](../includes/banner.md)]

Ten temat zawiera porady dotyczące importowania danych do arkusza finansowego przy użyciu jednostki Arkusz finansowy.

Jednostka Arkusz finansowy umożliwia importowanie tylko załączników, które mają typ konta lub konta przeciwstawnego **Księga**, **Odbiorca**, **Dostawca** lub **Bank**. Załącznik można wprowadzić w jednym wierszu, używając obu pól **Konto** i **Konto przeciwstawne**, lub w wielu wierszach, gdzie jest używane tylko pole **Konto** pole (a pole **Konto przeciwstawne** pozostaje puste w każdym wierszu). Jednostki Arkusz finansowy nie obsługuje każdego typu konta. Zamiast tego istnieją inne jednostki dla scenariuszy, w których są potrzebne inne kombinacje typów kont. Na przykład aby zaimportować transakcję projektu, należy użyć jednostki Arkusz wydatków w ramach projektu. Każda jednostka jest przeznaczona do obsługi konkretnych scenariuszy. Oznacza to, że w tych scenariuszach mogą być dostępne dodatkowe pola. Dodatkowe pola mogą być jednak niedostępne w jednostkach dla różnych scenariuszy.

## <a name="setup"></a>Konfiguracja
Przed wykonaniem importu przy użyciu jednostki Arkusz finansowy sprawdź następujące ustawienia:

- **Ustawienia numeracji partii arkusza** — Domyślnie podczas importowania za pomocą jednostki Arkusz finansowy numer partii arkusza wykorzystuje numerację zdefiniowaną w parametrach księgi głównej. Jeśli dla numerowania partii arkusza ustawisz wartość **Ręcznie**, domyślny numer nie jest stosowany. Ta konfiguracja nie jest obsługiwana.
- **Konfiguracja wymiaru finansowego** — Każda organizacja musi zdefiniować kolejność wymiarów finansowych dla sytuacji, gdy do importowania transakcji są używane jednostki. Kolejność definiuje się w oknie formatu **Integracja wymiarów księgi**, otwieranego ze ścieżki **Księga główna** &gt; **Plan kont** &gt; **Wymiary** &gt; **Konfiguracja wymiaru finansowego dla aplikacji integrujących** &gt; **Wybierz jednostki danych**. Segmenty importowanego konta księgowego muszą mieć taką samą kolejność. W przeciwnym wypadku podczas importu wystąpi błąd.

## <a name="general-journal-entity-setup"></a>Konfiguracja jednostek arkusza finansowego
Dwa ustawienia w obszarze roboczym Zarządzanie danymi mają wpływ na sposób stosowania domyślnego numeru partii arkusza lub numeru załącznika:

- **Przetwarzanie oparte na zestawie** (w jednostce danych)
- **Utworzone automatycznie** (w mapowaniu pól)

W poniższych sekcjach opisano wpływ tych ustawień. Wyjaśniają one także, w jaki sposób system generuje numery partii dla arkuszy i numerów załączników.

### <a name="journal-batch-number"></a>Arkusz z numerem partii

- Ustawienie **Przetwarzanie oparte na zestawie** w jednostce Arkusz finansowy nie wpływa na sposób generowania numerów partii arkusza.
- Jeśli w polu **Arkusz z numerem partii** zostanie ustawiona wartość **Utworzone automatycznie**, nowy numer partii arkusza jest tworzony dla każdego importowanego wiersza. To zachowanie nie jest zalecane. Ustawienie **Utworzone automatycznie** znajduje się w oknie importu projektu, w obszarze **Wyświetl mapę** na karcie **Szczegóły mapowania**.
- Jeśli w polu **Arkusz z numerem partii** nie ustawiono wartości **Utworzone automatycznie**, numer partii arkusza jest tworzony w następujący sposób:

    - Jeśli numer partii arkusza zdefiniowany w importowanym pliku pasuje do istniejącego, niezaksięgowanego arkusza dziennego, wszystkie wiersze o pasującym numerze partii arkusza są importowane do istniejącego arkusza. Wiersze nigdy nie są importowane do partii arkusza o zaksięgowanym numerze. Zamiast tego jest tworzony arkusz z nowym numerem.
    - Jeśli numer partii arkusza zdefiniowany w importowanym pliku nie pasuje do istniejącego, niezaksięgowanego arkusza dziennego, wszystkie wiersze mające ten sam numer partii arkusza są grupowane w nowym arkuszu. Na przykład wszystkie wiersze z numerem partii arkusza 1 są importowane do nowego arkusza, a wszystkie wiersze z numerem partii arkusza 2 są importowane do drugiego nowego arkusza. Numer partii arkusza jest tworzony przy użyciu numeracji zdefiniowanej w parametrach księgi głównej.

### <a name="voucher-number"></a>Numer załącznika

- W przypadku używania ustawienia **Przetwarzanie oparte na zestawie** zawartego w jednostce Arkusz finansowy należy w importowanym pliku podać numer załącznika. Każdej transakcji w arkuszu finansowym jest przypisywany numer załącznika pochodzący z importowanego pliku, nawet jeżeli załącznik nie jest zbilansowany. Zwróć uwagę na następne punkty, jeśli chcesz używać przetwarzania opartego na zestawie, ale również chcesz używać numeracji zdefiniowanej dla numerów załączników.

    - Aby włączyć tę funkcję, dla arkusza używanego do importowania w ustawieniu **Alokacja numerów podczas księgowania** zaznacz wartość **Tak**.
    - Numer załącznika i tak musi być zdefiniowany w importowanym pliku. Jednak ten numer ma charakter tymczasowy i będzie zastępowany przez numer załącznika podczas księgowania arkusza. Upewnij się, że wiersze arkusza są poprawnie pogrupowane według tymczasowego numeru załącznika. Na przykład podczas księgowania zostały znalezione trzy wiersze, które mają tymczasowy numer załącznika 1. Tymczasowy numer załącznika we wszystkich trzech wierszach jest zastępowany przez następny numer wynikający z numeracji. Jeśli te trzy wiersze nie są wpisem zbilansowanym, załącznik nie będzie księgowany. Następnie jeśli zostaną znalezione wiersze, które mają tymczasowy numer załącznika 2, ten numer jest zastępowany przez kolejny numer załącznika wynikający z sekwencji, i tak dalej.

- Jeśli nie używasz ustawienia **Przetwarzanie oparte na zestawie**, nie trzeba podawać numeru załącznika w importowanym pliku. Numery załączników są tworzone podczas importu na podstawie konfiguracji nazwy arkusza (**Tylko jeden załącznik**, **W połączeniu z bilansem** itd.). Na przykład jeśli nazwa arkusza jest zdefiniowana jako **W połączeniu z bilansem**, pierwszy wiersz otrzymuje nowy domyślny numer załącznika. Następnie system analizuje wiersz w celu określenia, czy zapisy debetowe są równe kredytowym. Jeśli w wierszu istnieje konto przeciwstawne, następny importowany wiersz otrzymuje nowy numer załącznika. Jeśli konto przeciwstawne nie istnieje, podczas importowania każdego nowego wiersza system analizuje, czy zapisy debetowe są równe kredytowym.
- Jeśli w polu **Numer załącznika** ustawiono wartość **Utworzone automatycznie**, import nie powiedzie się. Ustawienie **Utworzone automatycznie** nie jest obsługiwane dla pola **Numer załącznika**.

Domyślnie jednostka Arkusz finansowy używa przetwarzania opartego na zestawie. Po zbadaniu wymagań biznesowych organizacji można zmienić wartość ustawienia **Przetwarzanie oparte na zestawie**, klikając opcję **Jednostki danych** w obszarze roboczym **Zarządzanie danymi**. Przetwarzanie oparte na zestawie przyspiesza proces importowania. Jeśli nie używasz przetwarzania opartego na zestawie, importowanie jednostki Arkusz finansowy będzie wolniejsze.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]