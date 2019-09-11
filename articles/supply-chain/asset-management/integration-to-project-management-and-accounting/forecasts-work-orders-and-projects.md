---
title: Prognozy, zlecenia pracy i projekty
description: W tym temacie objaśniono prognozy i integrację zleceń pracy z modułem Zarządzanie projektami i ich księgowanie w module Zarządzanie składnikami majątku.
author: josaw1
manager: AnnBe
ms.date: 08/16/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 5e986d139ac9d0a7729bb9787f05332bcc09f59b
ms.sourcegitcommit: 109a6ef2d20758dc4a25c51b11e22dd2214a1cc4
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/16/2019
ms.locfileid: "1886823"
---
# <a name="forecasts-work-orders-and-projects"></a>Prognozy, zlecenia pracy i projekty

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

W module Zarządzanie składnikami majątku integracja z modułem **Zarządzanie projektami i ich księgowanie** odbywa się w celu zoptymalizowania kontroli kosztów, pozwalając użytkownikom na śledzenie kosztów dotyczących prognoz typów zadań konserwacji i zleceń pracy.

Aby śledzić prognozy typów zadań konserwacji, należy wykonać dwa ustawienia:

1. Wybierz projekt w **Zarządzanie składnikami majątku** > **Ustawienia** > **Parametry zarządzania składnikami majątku** > **Składniki majątku** link > **Projekt** skrócona karta > **Projekt prognozy konserwacji** pole.

2. W **Ustawienia domyślne typu zadania konserwacji** podczas tworzenia wiersza domyślnego typu zadania jest automatycznie tworzony numer działania dla wiersza (**Zarządzanie składnikami majątku** > **Ustawienia** > **Zadania** > **Ustawienia domyślne typu zadania konserwacji**).

Prognozy typu zadania konserwacji służą do dwóch celów: można śledzić koszty dla prognoz typów zadań konsewacji w module **Zarządzanie projektami i ich księgowanie**. Ponadto prognozy są automatycznie przenoszone do projektu zadania zlecenia pracy po wybraniu typu zadania konserwacji w zadaniu zlecenia.

Aby śledzić koszty zadań zlecenia pracy, należy najpierw skonfigurować projekty zleceń pracy. Opis procedury można znaleźć w sekcji [Ustawienia projektu zlecenia pracy](../setup-for-work-orders/work-order-project-setup.md).

## <a name="work-order-job-projects"></a>Projekty zadania zlecenia pracy

W przypadku tworzenia zadania zlecenia pracy w zleceniu pracy, projekt zlecenia jest określany na podstawie ustawień projektu nadrzędnego dla zlecenia pracy w **Zarządzanie składnikami majątku** > **Ustawienia** > **Zlecenia pracy** > **Ustawienia projektu**.

Projekty zadań zlecenia są tworzone przy użyciu kombinacji następujących informacji o zleceniu pracy:

- Typ zlecenia pracy wybrany w zleceniu pracy 
- Lokalizacja czynności konserwacyjnych związana z składnikiem majątku w zadaniu zlecenia pracy
- Typ składnika majątku związany z składnikiem majątku w zadaniu zlecenia pracy  
- Oczekiwany czas rozpoczęcia i zakończenia zlecenia pracy  

Istnieje możliwość, że nie wszystkie informacje wymienione powyżej znajdują się w zleceniu pracy. Dlatego wyszukiwanie projektu nadrzędnego zlecenia pracy jest wykonywane przy użyciu dostępnej kombinacji danych i wybierania identyfikatora projektu, który odpowiada danym zleceniom pracy.

Przykład: na poniższym rysunku ustawienie typu składnika majątku „silnik ciężarowy” oznacza, że każde zadanie zlecenia pracy utworzone w tym typie składnika będzie podprojektem o identyfikatorze projektu „000186”.

![Rysunek 1](media/01-integration-to-pma.png)

Cel identyfikatora projektu w zadaniu zlecenia pracy oraz powiązany numer działania (**Zarządzanie składnikami majątku** > **Wspólne** > **Zlecenia pracy** > **Wszystkie zlecenia pracy** > wybierz zlecenie pracy na liście > **Szczegóły wiersza** skrócona karta > pole **Identyfikator projektu** i pole **Numer działania** ) polega na śledzeniu kosztów związanych z zadaniem zlecenia pracy i zasobem wybranym na zleceniu pracy w module **Zarządzanie projektami i ich księgowanie**. 

Na poniższym rysunku widać graficzny przegląd projektów zleceń i powiązanych z nimi działań projektu.

![Rysunek 2](media/02-integration-to-pma.png)

Podczas tworzenia nowego zadania zlecenia pracy w zleceniu pracy automatycznie tworzony jest projekt zlecenia produkcyjnego. Wymiary finansowe dla składnika majątku związanego z zadaniem zlecenia są automatycznie przenoszone do projektu zlecenia pracy. Działanie projektu utworzone dla zadania zlecenia pracy ma dołączone do niego informacje dotyczące typu zadania konserwacji, wariantu typu zadania konserwacji oraz handlu. Te dane są przydatne, jeśli na przykład zamówienie zakupu jest tworzone na podstawie zlecenia pracy (patrz [Zaopatrzenie](../work-orders/procurement.md)) lub jeśli do rejestracji czasu jest używany moduł **Zarządzanie projektami i ich księgowanie**.  

Jeśli składnik majatku został zainstalowany w lokalizacji czynności konserwacyjnych, a ten składnik jest później instalowany w innej lokalizacji czynności konserwacyjnych, wymiary finansowe związane z nową lokalizacją czynności konserwacyjnych są automatycznie aktualizowane na tym składniku. Następnie podczas tworzenia zadania zlecenia pracy dla skłądnika majątku projekt zlecenia zadania automatycznie otrzymuje wymiary finansowe, które są obecnie powiązane z danym składnikiem. Oznacza to, że w przypadku korzystania z lokalizacji czynności konserwacyjnych koszty mogą być zawsze śledzone w lokalizacjach czynności konserwacyjnych, w których dany składnik został zainstalowany w danym momencie. Automatyczna aktualizacja wymiarów finansowych zapewnia pełne śledzenie kosztów związanych z kontrolowaniem i raportowaniem projektów.  


## <a name="work-order-projects-work-order-lifecycle-states-project-stages-and-project-types"></a>Projekty zleceń pracy, Stany cyklu życia zleceń pracy, etapy projektu i typy projektów

Aby zapewnić poprawne wykorzystanie stanów cyklu życia zlecenia pracy i powiązanych etapów projektu w zleceniach pracy, należy wziąć pod uwagę zależności w module **Zarządzanie projektami i ich księgowanie**:

- W module **Zarządzanie projektami i księgowanie** etapy projektu są ustawiane na typy projektów w **Parametry modułu Zarządzanie projektami i ich księgowanie**.  
- W **Parametry modułu Zarządzanie projektami i ich księgowanie** należy pamiętać o zaznaczeniu odpowiednich pól wyboru dla wszystkich typów projektów, które mają być używane. Na poniższym rysunku dla typów projektów **Utworzony** - **Oszacowanie** - **Zaplanowane** - **W toku** - **Zakończony** zostały wybrane dla typów pojektów „Czas i materiał” i „Wewnętrzne”. Te pięć etapów są istotne zarówno dla zadań konserwacji wewnętrznej, jak i konserwacji serwisowej  
- W **Zarządzanie składnikami majątku** typy projektów są definiowane przez grupy projektów skonfigurowane w formularzu ustawienia **Ustawienia projektu zlecenia pracy** > łącze **Grupa projektów**.  
- Ustawienia grup projektów w **Ustawienia projektu zlecenia pracy** są używane podczas tworzenia zleceń pracy. Podczas tworzenia nowego zlecenia pracy, projekt zlecenia pracy jest automatycznie tworzony dla danego zlecenia pracy.  
- Stany cyklu życia zlecenia pracy muszą mieć powiązany etap projektu.  
- Etap projektu związany ze stanem cyklu życia zlecenia pracy musi być zdefiniowany jako aktywny etap dla grupy projektów zdefiniowanej w projekcie zlecenia pracy. W zleceniu pracy automatycznie tworzony jest projekt zlecenia pracy.  
- W przypadku tworzenia nowego zlecenia pracy automatyczne przydzielanie projektu zlecenia pracy jest oparte na konfiguracji w **Ustawienia projektu zlecenia pracy** (**Zarządzanie składnikami majątku** > **Ustawienia** > **Zlecenia pracy** > **Ustawienia projektu**).  

Powiązania między grupami projektów zlecenia pracy, powiązane typy projektów, etapy projektu i Stany cyklu życia zlecenia pracy są przedstawione poniżej.  

![Rysunek 3](media/03-integration-to-pma.png)

![Rysunek 4](media/04-integration-to-pma.png)

![Rysunek 5](media/05-integration-to-pma.png)

Zapoznaj się z informacjami w [Ustawienia projektu zlecenia pracy](../setup-for-work-orders/work-order-project-setup.md) dotyczącymi konfigurowania projektów zleceń pracy oraz [Stany cyklu życia zlecenia pracy](../setup-for-work-orders/work-order-lifecycle-states.md) dotyczącymi sposobów tworzenia stanów cyklu życia zlecenia pracy.

Na poniższym rysunku przedstawiono graficzny przegląd różnych projektów utworzonych w module **Zarządzanie składnikami majątku** w celu umożliwienia integracji z modułem **Zarządzanie projektami i ich księgowanie**, a także procesów pracy, do których projekty są powiązane.

![Rysunek 6](media/06-integration-to-pma.png)

