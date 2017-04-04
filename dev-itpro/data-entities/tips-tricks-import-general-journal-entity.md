---
title: "Najważniejsze wskazówki dotyczące importowania załączników za pomocą dziennika głównego encji"
description: "Ten temat zawiera wskazówki do importowania danych do dziennika głównego przy użyciu ogólnego arkusza encji."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 94363
ms.assetid: 0b8149b5-32c5-4518-9ebd-09c9fd7f4cfc
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 4d6cf88788dcc5e982e509137aa444a020137a5e
ms.openlocfilehash: 81a52acd1d9baa12fcfe9d848441901894fa5682
ms.lasthandoff: 03/31/2017


---

# <a name="best-practices-for-importing-vouchers-using-the-general-journal-entity"></a>Najważniejsze wskazówki dotyczące importowania załączników za pomocą dziennika głównego encji

Ten temat zawiera wskazówki do importowania danych do dziennika głównego przy użyciu ogólnego arkusza encji.  

Jednostki dziennika głównego umożliwia importowanie załączników, które mają konta lub przesunięcie typ konta z **księgi, nabywcy, dostawcy lub banku**. Załącznik może być wprowadzana jako jeden wiersz, przy użyciu obu **konta** pola i **konto przeciwstawne** pole, lub jako wielu wierszach załącznika, gdzie tylko **konta** pole jest używane (i **konto przeciwstawne** jest puste w każdym wierszu). Jednostki dziennika głównego nie obsługuje każdego typu konta. Zamiast tego istnieją inne jednostki dla scenariuszy, w których są potrzebne inne kombinacje typów kont. Na przykład aby zaimportować transakcji projektu, należy użyć jednostki arkusza wydatków projektu. Każdy podmiot jest przeznaczony do obsługi określonych scenariuszy, co oznacza, że dodatkowe pola mogą być dostępne w jednostkach takich scenariuszy, ale nie w encje dla innego scenariusza.

## <a name="setup"></a>Konfiguracja
Przed zaimportowaniem za pomocą dziennika głównego encji, sprawdź następujące ustawienia:

-   **Ustawienia sekwencji numerów dla numeru partii dziennika** - domyślnie podczas importowania przy użyciu dziennika głównego obiektu, używa numerów partii dziennika sekwencji numerów, która jest zdefiniowana w parametrach księgi głównej. Jeśli dla numerowania partii arkusza ustawisz wartość **Ręcznie**, domyślny numer nie jest stosowany. Ta konfiguracja nie jest obsługiwana.
-   **Konfiguracja wymiaru finansowego** -każda organizacja należy zdefiniować odpowiednią kolejność wymiarów finansowych, gdy podmioty są używane do importowania transakcji. Kolejność jest zdefiniowany dla **księgi wymiary integracji** format, o **księgi głównej**&gt;**planu kont**&gt;**wymiary**&gt;**konfiguracji wymiaru finansowego do integrowania aplikacji**&gt;**wybierz encje danych**. Segmenty importowanego konta księgowego muszą mieć taką samą kolejność. W przeciwnym wypadku podczas importu wystąpi błąd.

## <a name="general-journal-entity-setup"></a>Konfiguracja jednostek arkusza finansowego
Dwa ustawienia zarządzania danymi mają wpływ na sposób zastosowania domyślny arkusz z numerem partii lub numer załącznika:

-   **Na podstawie zestawu przetwarzania** (w jednostce danych)
-   **Generowanie** (na mapowanie pól)

Poniższe sekcje opisują skutki użycia tych ustawień, a także sposób generowania numerów partii arkusza i numerów załączników.

### <a name="journal-batch-number"></a>Arkusz z numerem partii

-   Ustawienie **Przetwarzanie oparte na zestawie** w jednostce Arkusz finansowy nie wpływa na sposób generowania numerów partii arkusza.
-   Jeśli w polu **Arkusz z numerem partii** zostanie ustawiona wartość **Utworzone automatycznie**, nowy numer partii arkusza jest tworzony dla każdego importowanego wiersza. To zachowanie nie jest zalecane. Ustawienie **Utworzone automatycznie** znajduje się w oknie importu projektu, w obszarze **Wyświetl mapę** na karcie **Szczegóły mapowania**.
-   Jeśli w polu **Arkusz z numerem partii** nie ustawiono wartości **Utworzone automatycznie**, numer partii arkusza jest tworzony w następujący sposób:
    -   Jeśli arkusz z numerem partii, która jest zdefiniowana w importowanym pliku pasuje do istniejącego, niezaksięgowane arkusza dziennego w usłudze Microsoft Dynamics 365 dla operacji, wszystkie wiersze, które mają pasujące arkusz z numerem partii są importowane do istniejącego arkusza. Wiersze nigdy nie są importowane do partii arkusza o zaksięgowanym numerze. Zamiast tego jest tworzony arkusz z nowym numerem.
    -   Jeśli arkusz z numerem partii, która jest zdefiniowana w importowanym pliku nie odpowiada istniejącej, niezaksięgowane arkusza dziennego w usłudze Dynamics 365 dla operacji, wszystkie wiersze, które mają ten sam numer partii arkusza są grupowane pod nowy arkusz. Na przykład wszystkie wiersze z numerem partii arkusza 1 są importowane do nowego arkusza, a wszystkie wiersze z numerem partii arkusza 2 są importowane do drugiego nowego arkusza. Numer partii arkusza jest tworzony przy użyciu numeracji zdefiniowanej w parametrach księgi głównej.

### <a name="voucher-number"></a>Numer załącznika

-   W przypadku używania ustawienia **Przetwarzanie oparte na zestawie** zawartego w jednostce Arkusz finansowy należy w importowanym pliku podać numer załącznika. Każdej transakcji w arkuszu finansowym jest przypisywany numer załącznika pochodzący z importowanego pliku, nawet jeżeli załącznik nie jest zbilansowany. Jeśli chcesz użyć oparte na zestawie przetwarzania, ale również chcesz użyć sekwencji numerów, który jest zdefiniowany dla numerów załączników w usłudze Dynamics 365 dla operacji, dostarczono poprawki dla wersji 2016 lutego. Poprawka ma numer 3170316 i można ją pobrać z usługi Lifecycle Services (LCS). Aby uzyskać więcej informacji, zobacz [Pobieranie poprawek z portalu Lifecycle Services](..\migration-upgrade\download-hotfix-lcs.md).
    -   Aby włączyć tę funkcję, na nazwę arkusza, który jest używany przy przywozie w usłudze Dynamics 365 dla operacji, należy ustawić **numer alokacji przy księgowaniu** do **tak**.
    -   Numer załącznika i tak musi być zdefiniowany w importowanym pliku. Jednak liczba ta ma charakter tymczasowy i jest zastępowany przez 365 Dynamics dla operacji numeru załącznika podczas księgowania arkusza. Upewnij się, że wiersze arkusza są poprawnie pogrupowane według tymczasowego numeru załącznika. Na przykład podczas księgowania, trzy wiersze znajdują się, które mają tymczasowy numer załącznika 1. Numer załącznika tymczasowe wszystkich trzech linii jest zastępowany przez następny numer w sekwencji numerów. Jeśli te trzy wiersze nie są wpisem zbilansowanym, załącznik nie jest księgowany. Następnie jeśli zostaną znalezione wiersze, które mają tymczasowy numer załącznika 2, ten numer jest zastępowany przez kolejny numer załącznika wynikający z numeracji, i tak dalej.

<!-- -->

-   Gdy nie używasz **na podstawie zestawu przetwarzania** ustawienie, nie trzeba podać numer w importowanym pliku. Numery załączników są tworzone podczas importu na podstawie konfiguracji nazwy arkusza (**Tylko jeden załącznik**, **W połączeniu z bilansem** itd.). Na przykład jeśli nazwa arkusza jest zdefiniowana jako **W połączeniu z bilansem**, pierwszy wiersz otrzymuje nowy domyślny numer załącznika. Następnie system analizuje wiersz w celu określenia, czy zapisy debetowe są równe kredytowym. Jeśli w wierszu istnieje konto przeciwstawne, następny importowany wiersz otrzymuje nowy numer załącznika. Jeśli konto przeciwstawne nie istnieje, podczas importowania każdego nowego wiersza system analizuje, czy zapisy debetowe są równe kredytowym.
-   Jeśli w polu **Numer załącznika** ustawiono wartość **Utworzone automatycznie**, import nie powiedzie się. Ustawienie **Utworzone automatycznie** nie jest obsługiwane dla pola **Numer załącznika**.

Domyślnie jednostka Arkusz finansowy używa przetwarzania opartego na zestawie. Po zbadaniu wymagań biznesowych organizacji można zmienić wartość ustawienia **Przetwarzanie oparte na zestawie**, klikając opcję **Jednostki danych** w obszarze roboczym **Zarządzanie danymi**. Przetwarzanie oparte na zestawie przyspiesza proces importowania. Jeśli nie używasz przetwarzania opartego na zestawie, importowanie jednostki Arkusz finansowy będzie wolniejsze.


