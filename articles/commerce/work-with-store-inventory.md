---
title: Zarządzanie zapasami w sklepie
description: W tym temacie opisano typy dokumentów, których można używać do zarządzania zapasami.
author: rubencdelgado
manager: AnnBe
ms.date: 01/12/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.custom: 21391
ms.assetid: bfef3717-d0e0-491d-8466-d8a9c995177d
ms.search.region: global
ms.search.industry: Retail
ms.author: hhaines
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: 616fb8975543344657c00c419ce7279658694675
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2021
ms.locfileid: "4989483"
---
# <a name="commerce-inventory-management"></a>Zarządzanie zapasami handlowymi

[!include [banner](includes/banner.md)]

Podczas pracy z zapasami w Microsoft Dynamics 365 Commerce i korzystania z dowolnej aplikacji Commerce, która jest połączona z jednostką Commerce Scale Unit (CSU), ważne jest, aby wiedzieć, że logika przetwarzania zamówień w CSU zapewnia ograniczoną obsługę niektórych wymiarów magazynowych i niektórych zapasów typy przedmiotów. Aplikacje Commerce nie obsługują pełnego zakresu możliwości konfiguracji pozycji dostępnych w ramach opcji konfiguracji pozycji w rozwiązaniu Dynamics 365 Supply Chain Management.

Aplikacje Commerce działające w CSU nie obsługują następujących wymiarów produktów i konfiguracji towarów:

- Wymiar produktu konfiguracji i pozycje listy składowej (BOM) (z wyjątkiem produktów z zestawu detalicznego, które korzystają z niektórych składników struktury listy składowej BOM)
- Towary w ilości efektywnej
- Pozycje w wersjach kontrolowanych przez wymiary produktów

Aplikacje Commerce działające w CSU nie obsługują następujących wymiarów śledzenia:
- Wymiar właściciela

- Aplikacja punkt sprzedaży (POS) może oferuje ograniczoną obsługę następujących wymiarów. Punkt sprzedaż może automatycznie wprowadzać niektóre z tych wymiarów w transakcjach zapasów na podstawie konfiguracji ustawień magazynu lub sklepu. Jednak punkt sprzedaży nie obsługuje w pełni wymiarów w sposób, w jaki są one obsługiwane, jeśli transakcja sprzedaży jest ręcznie wprowadzana w module Commerce Headquarters. 

- **Lokalizacja w magazynie**— gdy jest używana nowa [operacja przychodząca](https://docs.microsoft.com/dynamics365/commerce/pos-inbound-inventory-operation) i [operacja wychodząca](https://docs.microsoft.com/dynamics365/commerce/pos-outbound-inventory-operation) punktu sprzedaży, użytkownicy mogą wybrać lokalizację zapasów magazynowych, w której będą przyjmowane pozycje lub z której będą wysyłane pozycje wychodzącego zamówienia przeniesienia. Jeśli zostanie użyta przestarzała operacja **pobranie i przyjęcie**, będzie dostępna ograniczona obsługa zarządzania lokalizacją na potrzeby przyjmowania i odbierania przeniesień wychodzących. Taka obsługa jest dostępna tylko po włączeniu opcji **Używaj procesu zarządzania magazynem** dla pozycji i magazynu sklepu. Lokalizacji zapasów nie można obecnie używać z operacją **Inwentaryzacja** ani operacją **Wyszukiwanie w magazynie**.

- **Numer identyfikacyjny** — stosowany tylko po włączeniu opcji **Używaj procesu zarządzania magazynem** dla pozycji i magazynu sklepu. W przypadku punktu sprzedaży, jeśli zapasy są przyjmowane do magazynu sklepu przy użyciu **operacji przychodzącej** lub operacji **pobrania i przyjęcia**, gdy proces zarządzania magazynem został włączony, i jeśli lokalizacja wybrana do przyjęcia pozycji została połączona z profilem lokalizacji wymagającym kontroli numeru identyfikacyjnego, aplikacja punktu sprzedaży będzie systematycznie stosować numer identyfikacyjny do wiersza przyjęcia. Użytkownicy punktu sprzedaży nie mogą zmieniać tych danych numeru identyfikacyjnego ani nimi zarządzać. Jeśli wymagane jest pełne zarządzanie numerami identyfikacyjnymi, zalecamy użycie w sklepie [aplikacji magazynu](https://docs.microsoft.com/dynamics365/supply-chain/warehousing/install-configure-warehousing-app) lub klienta narzędzi zaplecza do zarządzania przyjęciem pozycji.

- **Numer seryjny** — aplikacja punktu sprzedaży zapewnia ograniczoną obsługę rejestracji pojedynczego numeru seryjnego w wierszu transakcji sprzedaży dla zamówień utworzonych w punkcie sprzedaży i obejmujących pozycje serializowane. Ten numer seryjny nie jest sprawdzany względem zarejestrowanych numerów seryjnych, które już są w magazynie. Jeśli zamówienie sprzedaży jest tworzone w kanale biura obsługi lub realizowane za pośrednictwem zarządzania zasobów przedsiębiorstwa (ERP), a wiele numerów seryjnych jest rejestrowanych w jednym wierszu sprzedaży w trakcie procesu realizacji na platformie ERP, tych numerów seryjnych nie można zastosować ani sprawdzić, jeśli zwrot został przetworzony w punkcie sprzedaży dla tych zamówień. Gdy zapasy są przyjmowane przy użyciu **operacji przychodzącej**, użytkownicy mogą [rejestrować lub potwierdzać przyjęte numery seryjne](https://docs.microsoft.com/dynamics365/commerce/pos-serialized-items).

- **Identyfikator partii** — Aplikacja POS zapewnia ograniczoną obsługę podczas księgowania wyciągów, jeśli sprzedawany jest towar kontrolowany przez partię, ale użytkownicy POS nie mogą zdefiniować identyfikatora partii, która została sprzedana lub pobrana podczas korzystania z aplikacji POS.

- **Stan zapasów** — w przypadku towarów, które korzystają z procesu zarządzania magazynem i wymagają stanu zapasów, to pole stanu nie może być konfigurowane ani modyfikowane za pośrednictwem aplikacji punktu sprzedaży. Domyślny stan zapasów zdefiniowany w konfiguracji magazynu sklepu jest używany podczas przyjęcia pozycji do zapasów.

> [!NOTE]
> Wszystkie organizacje muszą przetestować konfiguracje pozycji za pośrednictwem aplikacji Commerce w środowiskach projektowych lub testowych przed wdrożeniem tych konfiguracji pozycji w środowiskach produkcyjnych. Przetestuj swoje produkty, używając ich do wykonywania regularnych transakcji sprzedaży typu cash-and-carry w POS i tworzenia zamówień klientów (jeśli dotyczy) za pośrednictwem POS, biur obsługi lub handlu elektronicznego, aby sprawdzić, czy mogą być w pełni obsługiwane. Należy również przetestować procesy dotyczące realizacji i zapasów w punkcie sprzedaży (takie jak operacje przyjmowania zapasów i realizacji zamówień) przed wdrożeniem nowych konfiguracji pozycji, aby upewnić się, że aplikacja punktu sprzedaży może je obsługiwać. Testowanie musi obejmować uruchomienie pełnego procesu księgowania wyciągów / zamówień w środowisku testowym i sprawdzenie, czy nie występują problemy z księgowaniem podczas tworzenia i księgowania zamówień na te pozycje w Commerce headquarters.
>
> Jeśli elementy są skonfigurowane w sposób, który nie jest obsługiwany przez aplikacje Commerce, a odpowiednie testy nie są wykonywane, mogą wystąpić awarie danych, których nie da się łatwo naprawić lub których nie da się w ogóle naprawić.

## <a name="purchase-orders"></a>Zamówienia zakupu

Zamówienia zakupu są tworzone w module Commerce Headquarters. Jeśli magazyn sklepu jest uwzględniony w nagłówku zamówienia zakupu lub w wierszach zamówienia zakupu, wiersze można przyjmować w sklepie przy użyciu [operacji przychodzącej](https://docs.microsoft.com/dynamics365/commerce/pos-inbound-inventory-operation) w punkcie sprzedaży. 

## <a name="transfer-orders"></a>Zamówienia przeniesienia

Zamówienia przeniesienia można tworzyć w module Commerce Headquarters, a także za pośrednictwem [operacji przychodzącej](https://docs.microsoft.com/dynamics365/commerce/pos-inbound-inventory-operation) lub [operacji wychodzącej](https://docs.microsoft.com/dynamics365/commerce/pos-outbound-inventory-operation) w punkcie sprzedaży. Za pomocą **operacji przychodzącej** punktu sprzedaży można utworzyć żądanie zamówienia przeniesienia, aby zapasy były wysyłane do sklepu z innego magazynu lub lokalizacji przechowywania. Za pomocą **operacji wychodzącej** punktu sprzedaży można utworzyć żądanie zamówienia przeniesienia, aby zapasy były wysyłane ze sklepu do innego magazynu lub lokalizacji przechowywania. Po utworzeniu zamówienia przeniesienia dla sklepu może on zarządzać przyjęciem zapasów dla zamówienia przeniesienia za pośrednictwem **operacji przychodzącej** w punkcie sprzedaży. Jeśli sklep wysyła zapasy do innej lokalizacji, **operacja wychodząca** w punkcie sprzedaży jest używana do zarządzania procesem wysyłki wychodzącej w sklepie.

## <a name="stock-counts"></a>Stany zapasów z inwentaryzacji

Inwentaryzacje mogą być zaplanowane lub niezaplanowane. Zaplanowane inwentaryzacje są tworzone za pośrednictwem modułu Commerce Headquarters przez utworzenie dokumentu arkusza zliczania połączonego z magazynem sklepu. Ten arkusz określa pozycje do zliczania. Sklep może następnie uzyskać dostęp do wstępnie zdefiniowanych arkuszy zliczania i wykonywać na nich działania, korzystając z operacji **Inwentaryzacja** w punkcie sprzedaży. Użytkownicy sklepu inicjują nieplanowaną inwentaryzację, ponieważ jest ona wymagana, jeśli używają oni operacji **Inwentaryzacja** w punkcie sprzedaży. W odróżnieniu od zaplanowanej inwentaryzacji inwentaryzacje niezaplanowane nie mają wstępnie zdefiniowanej listy pozycji. Po zakończeniu inwentaryzacji dowolnego typu w punkcie sprzedaży jest ona zatwierdzana i wysyłana do centrali. W centrali inwentaryzacja musi być następnie zweryfikowana i zaksięgowana w module Commerce Headquarters w ramach osobnego kroku.

## <a name="inventory-lookup"></a>Wyszukiwanie w magazynie

Ilość produktów dostępną obecnie w wielu sklepach i magazynach można wyświetlić na stronie **Wyszukiwanie w magazynie**. Oprócz bieżącej ilości dostępnej w zapasach można wyświetlić przyszłe dostępności zapasów (ATP) dla każdego sklepu. Wybierz sklep, dla którego chcesz wyświetlić ilości ATP, a następnie wybierz opcję **Pokaż dostępność sklepu**. Aby uzyskać informacje o dostępnych opcjach konfiguracji, zapoznaj się z tematem [Obliczanie dostępności zapasów dla kanałów sprzedaży detalicznej](https://docs.microsoft.com/dynamics365/commerce/calculated-inventory-retail-channels).


[!INCLUDE[footer-include](../includes/footer-banner.md)]