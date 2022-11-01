---
title: Zakończenie, publikacja i wdrożenie funkcji globalizacji
description: Ten artykuł zawiera informacje o cyklu życia funkcji globalizacji.
author: gionoder
ms.date: 12/15/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: gionoder
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.custom: ''
ms.assetid: ''
ms.search.form: ''
ms.openlocfilehash: 9d4a408f2169b220fefd9ab7e9f3b37217fb3cfe
ms.sourcegitcommit: 1ecfc1d8afb2201ab895ae6f93304ba2b120f14b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/21/2022
ms.locfileid: "9710843"
---
# <a name="complete-publish-and-deploy-a-globalization-feature"></a>Zakończenie, publikacja i wdrożenie funkcji globalizacji

[!include [banner](../includes/banner.md)]

## <a name="electronic-invoicing-feature-versions"></a>Wersje funkcji fakturowania elektronicznego

Funkcje fakturowania elektronicznego są wersjonowane. Po utworzeniu nowej wersji numer wersji jest automatycznie zwiększany.

Wersje funkcji fakturowania elektronicznego mają cykl życia, który ma maksymalnie trzy statusy:

- **Wersja robocza** — jeśli wersja funkcji ma ten stan, można edytować jej atrybuty konfiguracji oraz dowolne artefakty (na przykład konfiguracje formatów plików).
- **Zakończenie** — ten stan wskazuje, że zakończono edytowanie wersji funkcji i nie zamierzasz do tej wersji już do nich dochować zmian. Gdy wersja funkcji ma ten stan, nie można już edytować jej ani żadnego z jej komponentów.
- **Opublikowano** — Ten stan wskazuje, że wersja funkcji została opublikowana w globalnym repozytorium powiązanym z Twoją organizacją. Gdy wersja funkcji ma ten stan, nie można już edytować jej ani żadnego z jej komponentów.

W nowej wersji funkcji fakturowania elektronicznego można określić datę **wejścia w życie**. W ten sposób można zdefiniować wersję domyślną, która może zostać użyta lub zastąpiona, gdy funkcja jest wdrożona w środowisku usług.

Aby zmienić status wersji funkcji fakturowania elektronicznego, wykonaj następujące kroki.

1. Zaloguj się na konto usługi Regulatory Configuration Services (RCS).
2. Otwórz nowy obszar roboczy **Funkcja globalizacji**, a następnie w obszarze **Funkcje** wybierz kafelek **Faktury elektroniczne**.
3. Na stronie **Funkcje Faktur elektronicznych** po lewej, wybierz funkcję Faktur elektronicznych.
4. Na karcie **Wersje** po prawej stronie strony wybierz wersję.
5. Wybierz **opcję Zmiana stanu**, a następnie **wybierz opcję Ukończono** (jeśli bieżący stan to **Wersja robocza**) lub **Opublikowano** (jeśli bieżący stan to **Ukończono**).
6. W wyświetlonym oknie wiadomości z potwierdzeniem wybierz przycisk **Tak**.

Ręczna zmiana stanu z **Zakończone** na **Opublikowane** jest opcjonalna. Wersje funkcji fakturowania elektronicznego są automatycznie aktualizowane do **stanu Opublikowane**, gdy są wdrożone w środowisku usług.

Stan można śledzić w kolumnie **Stan wersji funkcji** na **karcie Wersje**.

## <a name="deploy-feature-versions"></a>Wdrażanie wersji funkcji

W usłudze RCS można użyć **polecenia Wdrożenie**, aby opublikować wersję funkcji fakturowania elektronicznego w docelowym środowisku usług lub połączonej aplikacji.

1. Na stronie **Funkcje Faktur elektronicznych** po lewej, wybierz funkcję Faktur elektronicznych.
2. Na karcie **Wersje** po prawej stronie strony wybierz wersję funkcji fakturowania elektronicznego, którą chcesz wdrożyć w środowisku usług lub połączonej aplikacji. Wybrana wersja musi mieć stan **Ukończono** lub **Opublikowana**.
3. Wybierz opcję **Rozmieszczaj**, a następnie wybierz jedną lub obie z następujących opcji w celu zdefiniowania celu wdrożenia:

    - **Połączona aplikacja** — jest to opcjonalne, ale musi być użyte, jeśli chcesz, by konfiguracja dostarczana przez instalację aplikacji była zapisana w wystąpieniu Microsoft Dynamics 365 Finance lub Dynamics 365 Supply Chain Management, które było wcześniej z nim skojarzone. Pominięcie wdrażania tego typu wymaga ręcznej konfiguracji parametrów zdefiniowanych w ustawieniach aplikacji Finance lub Supply Chain Management.
    - **Środowisko usługi** — wdraża funkcję fakturowania elektronicznego w środowisku usług. Fakturowanie elektroniczne jest wtedy gotowy do odbierania i przetwarzania dokumentów elektronicznych wysyłanych przez aplikacje finansowe i Supply Chain Management.

> [!NOTE]
> Zazwyczaj zmieniane są parametry funkcji raportowania elektronicznego, które muszą zostać wdrożone w środowisku serwisowym. Zmiany w połączonej aplikacji będą się zdarzać rzadko. Nowe wersje należy wdrażać w połączonej aplikacji tylko w przypadku zmiany odpowiednich parametrów aplikacji.

Aby określić, czy określoną wersję funkcji fakturowania elektronicznego wdrożono w określonym środowisku, należy zapoznać się z informacjami na karcie **Środowiska**.

## <a name="remove-feature-versions"></a>Usuwanie wersji funkcji

W RCS możesz wybrać **Anuluj**, aby usunąć określoną wersję funkcji fakturowania elektronicznego ze środowiska usługi, jeśli została tam wdrożona.

> [!IMPORTANT]
> Przycisk **Anuluj** działa tylko w przypadku środowisk serwisowych. Nie usuwa niczego z połączonej aplikacji dla bieżącej funkcji fakturowania elektronicznego.

## <a name="rebase-electronic-invoicing-features"></a>Zmiana bazy funkcji fakturowania elektronicznego

Gdy jedna funkcja fakturowania elektronicznego jest pochodną innej, możesz wybrać **Zmiana bazy**, aby zaktualizować pochodną funkcję o zmiany wprowadzone w pierwotnej (nadrzędnej) funkcji.

Aby ponownie utworzyć pochodną wersję utworzonej funkcji, należy wykonać następujące kroki.

1. Pobierz najnowszą wersję funkcji, importując ją z repozytorium globalnym. Aby uzyskać więcej informacji, zobacz temat [Funkcja importu z globalnego repozytorium](e-invoicing-import-feature-global-repository.md).
2. Z listy funkcji wybierz funkcję do zmiany podstawy.
3. Na karcie **Wersje** wybierz opcję **Nowa**, aby utworzyć wersję roboczą.
4. Wybierz opcję **Zmień podstawę**.
5. W oknie dialogowym **Zmiana podstawy** wybierz wersję funkcji, która ma być poddana zmianie podstawy.
6. Kliknij przycisk **OK**.
7. Przejrzyj składniki funkcji i wprowadź wymagane zmiany.
8. Aby zakończyć zmianę podstawy funkcji, wybierz opcję **Zmień stan**. Po zakończeniu zmiany podstawy można wykonać dodatkowe akcje.

## <a name="get-a-specific-version-of-electronic-invoicing-features"></a>Uzyskaj określoną wersję funkcji fakturowania elektronicznego

Podczas tworzenia nowej wersji funkcji fakturowania elektronicznego system tworzy kopię najnowszej wersji funkcji. Aby użyć wcześniejszej wersji funkcji jako podstawy nowej wersji, wybierz tę wersję, a następnie wybierz **polecenie Pobierz tę wersję**. Zostanie utworzona nowa wersja robocza funkcji, która jest kopią wybranej wersji.
