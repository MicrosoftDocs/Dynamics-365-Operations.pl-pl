---
title: Zmienianie waluty rozliczeniowej lub raportowania
description: W tym temacie wyjaśniono sposób zmiany waluty rozliczeniowej lub raportowania oraz dodawania waluty raportowania do konfiguracji księgi.
author: kweekley
ms.date: 05/05/2021
ms.topic: index-page
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2021-05-05
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 1fd641d4f60d8ff9710c89f43777f7fd8f378dbc6c73d773ac103f9d9f68e60e
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/05/2021
ms.locfileid: "6770600"
---
# <a name="change-the-accounting-or-reporting-currency"></a>Zmienianie waluty rozliczeniowej lub raportowania

[!include [banner](../includes/banner.md)]

W tym temacie wyjaśniono sposób zmiany waluty rozliczeniowej lub raportowania oraz dodawania waluty raportowania do konfiguracji księgi.

## <a name="symptom"></a>Objaw

Istnieje konieczność zmiany waluty rozliczeniowej lub raportowania lub dodania waluty raportowania do konfiguracji księgi. Tego rodzaju sytuacja ma zazwyczaj miejsce w następujących scenariuszach:

- W czasie konfigurowania firmy określono niewłaściwą walutę rozliczeniową lub walutę raportowania. Teraz trzeba zmienić tę walutę.
- Waluta raportowania została określona podczas konfigurowania firmy, ale organizacja chce ją teraz usunąć.
- Organizacja uaktualnia rozwiązanie Microsoft Dynamics 365 Finance lub przeprowadza migrację do niego i chce zmienić walutę rozliczeniową lub raportowania.

Organizacja, która nie używała dotychczas funkcji obsługi dwóch walut, chce rozpocząć korzystanie z niej. Tego rodzaju sytuacja ma zazwyczaj miejsce w scenariuszach opisanych poniżej.

- W czasie konfigurowania firmy nie określono waluty raportowania. (Waluta raportowania jest opcjonalna). Teraz okazało się, że dodanie waluty raportowania może okazać się przydatne.

## <a name="resolution"></a>Rozwiązanie

Najważniejsze jest to, czy w toku konfiguracji księgi w firmie zostały zaksięgowane jakiekolwiek transakcje (rzeczywiste lub budżetowe). **Jeśli dla firmy zostały zaksięgowane jakiekolwiek transakcje (rzeczywiste lub budżetowe), nie można zmienić waluty rozliczeniowej ani raportowania ani dodać waluty raportowania.** W zależności od tego, czy transakcje zostały zaksięgowane, wykonaj kroki opisane w jednej z poniższych sekcji.

### <a name="no-transactions-have-been-posted"></a>Nie zaksięgowano żadnych transakcji

1. W firmie, dla której aktualizowane są waluty, przejdź do ustawień **Księga główna \> Ustawienia księgi \> Księga**.
2. Na stronie **Księga** wybierz pozycję **Edytuj**.
3. Na skróconej karcie **Waluta** wybierz walutę rozliczeniową i walutę raportowania do użycia dla firmy.
4. Wybierz opcję **Zapisz**.

Jeśli pola waluty rozliczeniowej i waluty raportowania nie są dostępne na stronie **Księga**, w danej firmie została zaksięgowana co najmniej jedna transakcja (rzeczywista lub budżetowa). W związku z tym nie można zmieniać walut. W takim przypadku wykonaj kroki opisane w następnej sekcji.

### <a name="transactions-have-been-posted"></a>Zaksięgowano transakcje

**Jeśli w firmie zostały zaksięgowane transakcje, jedynym sposobem na zmianę lub dodanie walut księgowania lub raportowania jest utworzenie nowej firmy z poprawnymi walutami.** W celu ułatwienia tego procesu moduł Zarządzanie danymi w systemie umożliwia skopiowanie rekordów konfiguracji i rekordów głównych z bieżącej do nowej firmy.

Zmiany walut księgowania i raportowania mają zastosowanie w całym systemie. Mają zastosowanie nie tylko do księgi głównej, ale także do wszystkich ksiąg podrzędnych (Rozrachunki z odbiorcami, Rozrachunki z dostawcami, Zapasy, Projekt itp.), wszystkich rozwiązań niezależnych dostawców oprogramowania (ISV) i wszelkich wprowadzonych przez użytkownika rozszerzeń zawierających kwoty.

Proces znajdowania i przeliczania poszczególnych kwot na inną walutę może wiązać się z błędami. W związku z tym zespół inżynierów nie zatwierdzi skryptu, który zmienia lub dodaje waluty księgowania i raportowania. Ponadto choć narzędzie, które było dostępne dla rozwiązania Microsoft Dynamics AX 2012, umożliwiało zmienianie i dodawanie walut księgowania i raportowania, to jest ono już przestarzałe i zostało wycofane zarówno dla rozwiązania AX 2012 R3, jak i dla rozwiązania Finance.

Aby skopiować dane ustawień i dane główne z bieżącej do nowej firmy, należy wykonać kroki opisane poniżej.

1. Kliknij kolejno opcje **Obszary robocze \> Zarządzanie danymi**.
2. Wybierz **Szablony** w grupie **Import/eksport**.
3. Upewnij się, że szablony są dostępne. Jeśli żadne szablony nie są dostępne, zaznacz opcję **Załaduj szablony domyślne** i poczekaj na wygenerowanie szablonów.
4. Wróć do obszaru roboczego **Zarządzanie danymi**.
5. Wybierz pozycję **Kopiuj do firmy**.
6. Nadaj grupie nazwę i wprowadź jej opis.
7. W polu **Firma źródłowa** wybierz firmę, z której chcesz skopiować dane.
8. Na skróconej karcie **Firmy docelowe** wybierz pozycję **Utwórz firmy**, aby utworzyć nową firmę, do której będzie można skopiować dane firmy źródłowej. Wybierz opcję **Wybierz istniejącą**, aby skopiować dane do istniejącej firmy.
9. Opcjonalnie: ustaw dla pola **Kopiuj sekwencje numerów** wartość **Tak**. (Ten krok jest zalecany w przypadku kopiowania danych).
10. W obszarze **Wybrane jednostki** wybierz pozycję **Dodaj szablon**.
11. Wybierz szablon, którego chcesz użyć. Sugerowane szablony dla nowej firmy to **025 — Księga główna** i **Finanse**. Zaleca się przejrzenie wszystkich innych dostępnych szablonów w celu ustalenia, czy żaden z nich nie spełnia odpowiednich wymagań.
12. Wybierz pozycję **Kopiuj do firmy**, aby uruchomić proces wsadowy, w ramach którego zostaną utworzone wybrane jednostki, a następnie skopiuj je do firmy docelowej.
13. Po zakończeniu procesu, ale przed zaksięgowaniem dowolnej transakcji, przejdź do księgi i zaktualizuj waluty rozliczeniową i raportowania zgodnie z opisem z wcześniejszej części tego tematu.

W przypadku utworzenia nowej firmy w celu zmiany waluty rozliczeniowej lub raportowania upewnij się, że salda początkowe są przeliczane z walut starej firmy na nowe waluty.

Aby obejrzeć film, który pokazuje powyższe czynności, zobacz temat [Kopiuj do firmy](https://community.dynamics.com/365/b/techtalks/posts/copy-into-legal-entity-october-24-2017).
