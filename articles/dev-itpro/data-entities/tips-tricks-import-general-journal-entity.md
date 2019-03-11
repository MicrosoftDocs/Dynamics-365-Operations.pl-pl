---
title: Najlepsze rozwiązania w zakresie importowania załączników za pomocą jednostki Arkusz finansowy
description: Ten temat zawiera porady dotyczące importowania danych do arkusza finansowego przy użyciu jednostki Arkusz finansowy.
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 94363
ms.assetid: 0b8149b5-32c5-4518-9ebd-09c9fd7f4cfc
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 29cb4b940875b96cabaff540360674da528f8f39
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/29/2019
ms.locfileid: "322520"
---
# <a name="best-practices-for-importing-vouchers-by-using-the-general-journal-entity"></a>Najlepsze rozwiązania w zakresie importowania załączników za pomocą jednostki Arkusz finansowy

[!include [banner](../includes/banner.md)]

Ten temat zawiera porady dotyczące importowania danych do arkusza finansowego przy użyciu jednostki Arkusz finansowy.

Jednostka Arkusz finansowy umożliwia importowanie tylko załączników, które mają typ konta lub konta przeciwstawnego **Księga, Odbiorca, Dostawca, lub Bank**. Załącznik można wprowadzić w jednym wierszu, używając obu pól **Konto** i **Konto przeciwstawne**, lub w wielu wierszach, gdzie jest używane tylko pole **Konto** pole (a pole **Konto przeciwstawne** pozostaje puste w każdym wierszu). Jednostki Arkusz finansowy nie obsługuje każdego typu konta. Zamiast tego istnieją inne jednostki dla scenariuszy, w których są potrzebne inne kombinacje typów kont. Na przykład aby zaimportować transakcję projektu, należy użyć jednostki Arkusz wydatków w ramach projektu. Każda jednostka jest zaprojektowana do obsługi określonych scenariuszy, co oznacza, że określone pola mogą być dostępne w jednostkach dla takich scenariuszy, ale nie w jednostkach dla innych scenariuszy.

## <a name="setup"></a>Konfiguracja
Przed wykonaniem importu przy użyciu jednostki Arkusz finansowy sprawdź następujące ustawienia:

- **Ustawienia numeracji partii arkusza** — Domyślnie podczas importowania za pomocą jednostki Arkusz finansowy numer partii arkusza wykorzystuje numerację zdefiniowaną w parametrach księgi głównej. Jeśli dla numerowania partii arkusza ustawisz wartość **Ręcznie**, domyślny numer nie jest stosowany. Ta konfiguracja nie jest obsługiwana.
- **Konfiguracja wymiaru finansowego** — Każda organizacja musi zdefiniować kolejność wymiarów finansowych dla sytuacji, gdy do importowania transakcji są używane jednostki. Kolejność definiuje się w oknie formatu **Integracja wymiarów księgi**, otwieranego ze ścieżki **Księga główna** &gt; **Plan kont** &gt; **Wymiary** &gt; **Konfiguracja wymiaru finansowego dla aplikacji integrujących** &gt; **Wybierz jednostki danych**. Segmenty importowanego konta księgowego muszą mieć taką samą kolejność. W przeciwnym wypadku podczas importu wystąpi błąd.

## <a name="general-journal-entity-setup"></a>Konfiguracja jednostek arkusza finansowego
Dwa ustawienia w obszarze roboczym Zarządzanie danymi mają wpływ na sposób stosowania domyślnego numeru partii arkusza lub numeru załącznika:

- **Przetwarzanie oparte na zestawie** (w jednostce danych)
- **Utworzone automatycznie** (w mapowaniu pól)

Poniższe sekcje opisują skutki użycia tych ustawień, a także sposób generowania numerów partii arkusza i numerów załączników.

### <a name="journal-batch-number"></a>Arkusz z numerem partii

- Ustawienie **Przetwarzanie oparte na zestawie** w jednostce Arkusz finansowy nie wpływa na sposób generowania numerów partii arkusza.
- Jeśli w polu **Arkusz z numerem partii** zostanie ustawiona wartość **Utworzone automatycznie**, nowy numer partii arkusza jest tworzony dla każdego importowanego wiersza. To zachowanie nie jest zalecane. Ustawienie **Utworzone automatycznie** znajduje się w oknie importu projektu, w obszarze **Wyświetl mapę** na karcie **Szczegóły mapowania**.
- Jeśli w polu **Arkusz z numerem partii** nie ustawiono wartości **Utworzone automatycznie**, numer partii arkusza jest tworzony w następujący sposób:

    - Jeśli numer partii arkusza zdefiniowany w importowanym pliku pasuje do istniejącego, niezaksięgowanego arkusza dziennego, wszystkie wiersze o pasującym numerze partii arkusza są importowane do istniejącego arkusza. Wiersze nigdy nie są importowane do partii arkusza o zaksięgowanym numerze. Zamiast tego jest tworzony arkusz z nowym numerem.
    - Jeśli numer partii arkusza zdefiniowany w importowanym pliku nie pasuje do istniejącego, niezaksięgowanego arkusza dziennego, wszystkie wiersze mające ten sam numer partii arkusza są grupowane w nowym arkuszu. Na przykład wszystkie wiersze z numerem partii arkusza 1 są importowane do nowego arkusza, a wszystkie wiersze z numerem partii arkusza 2 są importowane do drugiego nowego arkusza. Numer partii arkusza jest tworzony przy użyciu numeracji zdefiniowanej w parametrach księgi głównej.

### <a name="voucher-number"></a>Numer załącznika

- W przypadku używania ustawienia **Przetwarzanie oparte na zestawie** zawartego w jednostce Arkusz finansowy należy w importowanym pliku podać numer załącznika. Każdej transakcji w arkuszu finansowym jest przypisywany numer załącznika pochodzący z importowanego pliku, nawet jeżeli załącznik nie jest zbilansowany. Jeśli chcesz używać przetwarzania opartego na zestawie, ale również chcesz używać numeracji zdefiniowanej dla numerów załączników, przygotowano poprawkę w wydaniu z lutego 2016 r. Poprawka ma numer 3170316 i można ją pobrać z usługi Lifecycle Services (LCS). Aby uzyskać więcej informacji, zobacz [Pobieranie poprawek z portalu Lifecycle Services](../migration-upgrade/download-hotfix-lcs.md).

    - Aby włączyć tę funkcję, dla arkusza używanego do importowania w ustawieniu **Alokacja numerów podczas księgowania** zaznacz wartość **Tak**.
    - Numer załącznika i tak musi być zdefiniowany w importowanym pliku. Jednak ten numer ma charakter tymczasowy i jest zastępowany przez numer załącznika podczas księgowania arkusza. Upewnij się, że wiersze arkusza są poprawnie pogrupowane według tymczasowego numeru załącznika. Na przykład podczas księgowania zostały znalezione trzy wiersze, które mają tymczasowy numer załącznika 1. Tymczasowy numer załącznika we wszystkich trzech wierszach jest zastępowany przez następny numer wynikający z numeracji. Jeśli te trzy wiersze nie są wpisem zbilansowanym, załącznik nie jest księgowany. Następnie jeśli zostaną znalezione wiersze, które mają tymczasowy numer załącznika 2, ten numer jest zastępowany przez kolejny numer załącznika wynikający z numeracji, i tak dalej.

- Jeśli nie używasz ustawienia **Przetwarzanie oparte na zestawie**, nie trzeba podawać numeru załącznika w importowanym pliku. Numery załączników są tworzone podczas importu na podstawie konfiguracji nazwy arkusza (**Tylko jeden załącznik**, **W połączeniu z bilansem** itd.). Na przykład jeśli nazwa arkusza jest zdefiniowana jako **W połączeniu z bilansem**, pierwszy wiersz otrzymuje nowy domyślny numer załącznika. Następnie system analizuje wiersz w celu określenia, czy zapisy debetowe są równe kredytowym. Jeśli w wierszu istnieje konto przeciwstawne, następny importowany wiersz otrzymuje nowy numer załącznika. Jeśli konto przeciwstawne nie istnieje, podczas importowania każdego nowego wiersza system analizuje, czy zapisy debetowe są równe kredytowym.
- Jeśli w polu **Numer załącznika** ustawiono wartość **Utworzone automatycznie**, import nie powiedzie się. Ustawienie **Utworzone automatycznie** nie jest obsługiwane dla pola **Numer załącznika**.

Domyślnie jednostka Arkusz finansowy używa przetwarzania opartego na zestawie. Po zbadaniu wymagań biznesowych organizacji można zmienić wartość ustawienia **Przetwarzanie oparte na zestawie**, klikając opcję **Jednostki danych** w obszarze roboczym **Zarządzanie danymi**. Przetwarzanie oparte na zestawie przyspiesza proces importowania. Jeśli nie używasz przetwarzania opartego na zestawie, importowanie jednostki Arkusz finansowy będzie wolniejsze.
