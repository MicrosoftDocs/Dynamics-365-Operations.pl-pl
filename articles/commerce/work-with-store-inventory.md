---
title: Zarządzanie zapasami w sklepie
description: W tym temacie opisano typy dokumentów, których można używać do zarządzania zapasami.
author: rubencdelgado
manager: AnnBe
ms.date: 05/15/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 21391
ms.assetid: bfef3717-d0e0-491d-8466-d8a9c995177d
ms.search.region: global
ms.search.industry: Retail
ms.author: rubendel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: a3e6450c358d12dc62c2ffa20e7ff529be86bbe5
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "4414955"
---
# <a name="store-inventory-management"></a>Zarządzanie zapasami w sklepie

[!include [banner](includes/banner.md)]

Jeśli pracujesz z zapasami w aplikacji Microsoft Dynamics 365 Commerce i używasz aplikacji punktu sprzedaży, pamiętaj, że w punkt sprzedaży oferuje ograniczoną obsługę niektórych wymiarów magazynowych i niektórych typów pozycji magazynowych. Aplikacja punktu sprzedaży nie obsługuje pełnego zakresu możliwości konfiguracji pozycji dostępnych w ramach opcji konfiguracji pozycji w rozwiązaniu Dynamics 365 Supply Chain Management.

Obecnie rozwiązanie punktu sprzedaży nie obsługuje następujących wymiarów produktu i konfiguracji pozycji:

- Wymiar produktu konfiguracji i pozycje listy składowej (BOM) (z wyjątkiem produktów z zestawu detalicznego, które korzystają z niektórych składników struktury listy składowej BOM)
- Towary w ilości efektywnej
- Pozycje w wersjach kontrolowanych przez wymiary produktów

Aplikacja punktu sprzedaży aktualnie nie obsługuje następujących wymiarów śledzenia w punkcie sprzedaży:

- Wymiar śledzenia partii
- Wymiar właściciela

Punkt sprzedaży zapewnia ograniczoną obsługę następujących wymiarów. Mówiąc inaczej, punkt sprzedaż może automatycznie wprowadzać niektóre z tych wymiarów w transakcjach zapasów na podstawie konfiguracji ustawień magazynu lub sklepu. Punkt sprzedaży nie obsługuje w pełni wymiarów w sposób, w jaki są one obsługiwane, jeśli transakcja sprzedaży jest ręcznie wprowadzana w module Commerce Headquarters. 

- **Lokalizacja w magazynie**— gdy jest używana nowa [operacja przychodząca](https://docs.microsoft.com/dynamics365/commerce/pos-inbound-inventory-operation) i [operacja wychodząca](https://docs.microsoft.com/dynamics365/commerce/pos-outbound-inventory-operation) punktu sprzedaży, użytkownicy mogą wybrać lokalizację zapasów magazynowych, w której będą przyjmowane pozycje lub z której będą wysyłane pozycje wychodzącego zamówienia przeniesienia. Jeśli zostanie użyta przestarzała operacja **pobranie i przyjęcie**, będzie dostępna ograniczona obsługa zarządzania lokalizacją na potrzeby przyjmowania i odbierania przeniesień wychodzących. Taka obsługa jest dostępna tylko po włączeniu opcji **Używaj procesu zarządzania magazynem** dla pozycji i magazynu sklepu. Lokalizacji zapasów nie można obecnie używać z operacją **Inwentaryzacja** ani operacją **Wyszukiwanie w magazynie**.
- **Numer identyfikacyjny** — stosowany tylko po włączeniu opcji **Używaj procesu zarządzania magazynem** dla pozycji i magazynu sklepu. W przypadku punktu sprzedaży, jeśli zapasy są przyjmowane do magazynu sklepu przy użyciu **operacji przychodzącej** lub operacji **pobrania i przyjęcia**, gdy proces zarządzania magazynem został włączony, i jeśli lokalizacja wybrana do przyjęcia pozycji została połączona z profilem lokalizacji wymagającym kontroli numeru identyfikacyjnego, aplikacja punktu sprzedaży będzie systematycznie stosować numer identyfikacyjny do wiersza przyjęcia. Użytkownicy punktu sprzedaży nie mogą zmieniać tych danych numeru identyfikacyjnego ani nimi zarządzać. Jeśli wymagane jest pełne zarządzanie numerami identyfikacyjnymi, zalecamy użycie w sklepie [aplikacji magazynu](https://docs.microsoft.com/dynamics365/supply-chain/warehousing/install-configure-warehousing-app) lub klienta narzędzi zaplecza do zarządzania przyjęciem pozycji.
- **Numer seryjny** — aplikacja punktu sprzedaży zapewnia ograniczoną obsługę rejestracji pojedynczego numeru seryjnego w wierszu transakcji sprzedaży dla zamówień utworzonych w punkcie sprzedaży i obejmujących pozycje serializowane. Ten numer seryjny nie jest sprawdzany względem zarejestrowanych numerów seryjnych, które już są w magazynie. Jeśli zamówienie sprzedaży jest tworzone w kanale biura obsługi lub realizowane za pośrednictwem zarządzania zasobów przedsiębiorstwa (ERP), a wiele numerów seryjnych jest rejestrowanych w jednym wierszu sprzedaży w trakcie procesu realizacji na platformie ERP, tych numerów seryjnych nie można zastosować ani sprawdzić, jeśli zwrot został przetworzony w punkcie sprzedaży dla tych zamówień. Gdy zapasy są przyjmowane przy użyciu **operacji przychodzącej**, użytkownicy mogą [rejestrować lub potwierdzać przyjęte numery seryjne](https://docs.microsoft.com/dynamics365/commerce/pos-serialized-items).
- **Stan zapasów** — w przypadku towarów, które korzystają z procesu zarządzania magazynem i wymagają stanu zapasów, to pole stanu nie może być konfigurowane ani modyfikowane za pośrednictwem aplikacji punktu sprzedaży. Domyślny stan zapasów zdefiniowany w konfiguracji magazynu sklepu jest używany podczas przyjęcia pozycji do zapasów.

> [!NOTE]
> Wszystkie organizacje muszą przetestować konfiguracje pozycji za pośrednictwem punktu sprzedaży w środowiskach projektowych lub testowych przed wdrożeniem tych konfiguracji pozycji w środowiskach produkcyjnych. Przetestuj pozycje, używając jej do przeprowadzenia zwykłych transakcji sprzedaży kasowej i tworząc zamówienia odbiorcy (jeśli ma to zastosowanie) za pośrednictwem punktu sprzedaży. Należy również przetestować procesy dotyczące realizacji i zapasów w punkcie sprzedaży (takie jak operacje przyjmowania zapasów i realizacji zamówień) przed wdrożeniem nowych konfiguracji pozycji, aby upewnić się, że aplikacja punktu sprzedaży może je obsługiwać. Testowanie musi obejmować uruchomienie pełnego procesu księgowania zestawienia w środowisku testowym oraz sprawdzenie, czy nie występują problemy podczas tworzenia i księgowania zamówień dla pozycji w module Commerce Headquarters.
>
> Jeśli pozycje są skonfigurowane w sposób nieobsługiwany przez aplikację punktu sprzedaży, a odpowiednie testy nie zostaną przeprowadzone, w trakcie procesu tworzenia zamówień mogą wystąpić błędy danych, których nie można łatwo skorygować lub które nie są objęte standardową obsługą produktu.

## <a name="purchase-orders"></a>Zamówienia zakupu

Zamówienia zakupu są tworzone w module Commerce Headquarters. Jeśli magazyn sklepu jest uwzględniony w nagłówku zamówienia zakupu lub w wierszach zamówienia zakupu, wiersze można przyjmować w sklepie przy użyciu [operacji przychodzącej](https://docs.microsoft.com/dynamics365/commerce/pos-inbound-inventory-operation) w punkcie sprzedaży. 

## <a name="transfer-orders"></a>Zamówienia przeniesienia

Zamówienia przeniesienia można tworzyć w module Commerce Headquarters, a także za pośrednictwem [operacji przychodzącej](https://docs.microsoft.com/dynamics365/commerce/pos-inbound-inventory-operation) lub [operacji wychodzącej](https://docs.microsoft.com/dynamics365/commerce/pos-outbound-inventory-operation) w punkcie sprzedaży. Za pomocą **operacji przychodzącej** punktu sprzedaży można utworzyć żądanie zamówienia przeniesienia, aby zapasy były wysyłane do sklepu z innego magazynu lub lokalizacji przechowywania. Za pomocą **operacji wychodzącej** punktu sprzedaży można utworzyć żądanie zamówienia przeniesienia, aby zapasy były wysyłane ze sklepu do innego magazynu lub lokalizacji przechowywania. Po utworzeniu zamówienia przeniesienia dla sklepu może on zarządzać przyjęciem zapasów dla zamówienia przeniesienia za pośrednictwem **operacji przychodzącej** w punkcie sprzedaży. Jeśli sklep wysyła zapasy do innej lokalizacji, **operacja wychodząca** w punkcie sprzedaży jest używana do zarządzania procesem wysyłki wychodzącej w sklepie.

## <a name="stock-counts"></a>Stany zapasów z inwentaryzacji

Inwentaryzacje mogą być zaplanowane lub niezaplanowane. Zaplanowane inwentaryzacje są tworzone za pośrednictwem modułu Commerce Headquarters przez utworzenie dokumentu arkusza zliczania połączonego z magazynem sklepu. Ten arkusz określa pozycje do zliczania. Sklep może następnie uzyskać dostęp do wstępnie zdefiniowanych arkuszy zliczania i wykonywać na nich działania, korzystając z operacji **Inwentaryzacja** w punkcie sprzedaży. Użytkownicy sklepu inicjują nieplanowaną inwentaryzację, ponieważ jest ona wymagana, jeśli używają oni operacji **Inwentaryzacja** w punkcie sprzedaży. W odróżnieniu od zaplanowanej inwentaryzacji inwentaryzacje niezaplanowane nie mają wstępnie zdefiniowanej listy pozycji. Po zakończeniu inwentaryzacji dowolnego typu w punkcie sprzedaży jest ona zatwierdzana i wysyłana do centrali. W centrali inwentaryzacja musi być następnie zweryfikowana i zaksięgowana w module Commerce Headquarters w ramach osobnego kroku.

## <a name="inventory-lookup"></a>Wyszukiwanie w magazynie

Ilość produktów dostępną obecnie w wielu sklepach i magazynach można wyświetlić na stronie **Wyszukiwanie w magazynie**. Oprócz bieżącej ilości dostępnej w zapasach można wyświetlić przyszłe dostępności zapasów (ATP) dla każdego sklepu. Wybierz sklep, dla którego chcesz wyświetlić ilości ATP, a następnie wybierz opcję **Pokaż dostępność sklepu**. Aby uzyskać informacje o dostępnych opcjach konfiguracji, zapoznaj się z tematem [Obliczanie dostępności zapasów dla kanałów sprzedaży detalicznej](https://docs.microsoft.com/dynamics365/commerce/calculated-inventory-retail-channels).
