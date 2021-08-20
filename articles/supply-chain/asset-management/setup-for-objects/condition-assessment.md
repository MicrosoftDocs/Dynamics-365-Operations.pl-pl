---
title: Ocena warunku
description: W tym temacie wyjaśniono, jak utworzyć szablon oceny warunku i jak zarejestrować składnik majątku w Zarządzaniu składnikami majątku.
author: johanhoffmann
ms.date: 06/26/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage, EntAssetObjectCondition, EntAssetConditionTemplate
audience: Application User
ms.reviewer: kamaybac
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: cced322dd2f213d8e6025d853edc8472618989b61de7139b28ba1c6bffd3ad2a
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/05/2021
ms.locfileid: "6736071"
---
# <a name="condition-assessment"></a>Ocena warunku

[!include [banner](../../includes/banner.md)]

 

W tym temacie wyjaśniono, jak utworzyć szablon oceny warunku i jak zarejestrować składnik majątku w Zarządzaniu składnikami majątku. Ocena stanu jest wykonywana w regularnych odstępach czasu, a podstawowym celem jest tworzenie i utrzymywanie danych o stanie składników majątku. Z punktu widzenia konserwacji zapobiegawczej ważne jest monitorowanie kluczowych informacji, takich jak aktualny stan i pozostały okres eksploatacji. Ponadto, jeśli przeprowadzą Państwo ocenę stanu w regularnych odstępach czasu, będą Państwo mogli monitorować i porównywać warunki na maszynie w fabryce.

Ocena stanu może być wykorzystana do pomiaru i monitorowania wielu warunków na sprzęcie. Przykład: można zmierzyć drgania maszyny. Po zarejestrowaniu pomiarów drgań w zarządzaniu składnikami majątku, na różnego rodzaju sprzęcie można wyszukać najnowszą zarejestrowaną ocenę i wyświetlić pomiary drgań.

Tworzona jest ocena stanu składników majątku. Przed wykonaniem procedury oceny warunków należy skonfigurować szablon oceny warunków dla danego typu składnika majątku. Powodem stosowania szablonów do oceny stanu jest uniknięcie zmienności danych dotyczących podobnych składników majątku. Kolejność konfigurowania i używania oceny stanu w zarządzaniu składnikami majątku to: najpierw należy skonfigurować wymagane szablony oceny warunków. Następnie skojarz szablony z typami składników majątku w formularzu **typy składników majątku**. Na koniec można utworzyć rejestracje oceny warunku dla zasobu w formularzu **składnika majątku**.

## <a name="create-a-condition-assessment-template"></a>Tworzenie szablonu oceny warunku

1. Wybierz **Zarządzanie składnikami majątku** > **Ustawienia** > **Typy składników majątku** > **Ocena warunku**.
2. Wybierz pozycję **Nowy**, aby utworzyć nowy szablon.
3. Wstaw identyfikator szablonu w polu **Szablon**.
4. Wstaw nazwę szablonu w polu **Nazwa**.
5. Na skróconej karcie **Wiersze oceny warunku** dodaj wiersze wymagane do oceny warunku, w tym wybór odpowiedniego typu warunku i jednostkę miary.
6. Na skróconej karcie **Typy składników majątku** dodaj typy składników majątku, dla których ma być używany ten szablon oceny warunku.
7. W polach **Wiersze** i **Typy składników majątku** w grupie **Szczegóły** u góry ekranu zobaczysz wiersze oceny i typów składników majątku związanych z wybranym szablonem oceny warunku.


## <a name="create-condition-assessment-registration-on-an-asset"></a>Tworzenie rejestracji oceny warunku dla składnika majątku

1. Wybierz **Zarządzanie składnikami majątku** > **Wspólne** > **Składniki majątku** > **Wszystkie składniki majątku**.
2. Na liście wybierz składnik majątku, dla którego chcesz utworzyć rejestrację oceny warunku.
3. Na karcie **Ogólne** kliknij przycisk **Ocena warunku**.
4. Kliknij przycisk **Nowy**, aby dodać nową rejestrację.
5. Wybierz datę oceny warunku w polu **Data.**
6. Wybierz imię i nazwisko pracownika, który przeprowadził rejestrację oceny w polu **pracownik.**
7. W polu **wiersze** jest widoczna liczba wierszy oceny, które zostały skonfigurowane w ramach oceny warunku.
8. Wybierz szablon dla oceny warunku w polu **Szablon**. Nazwa szablonu zostanie automatycznie wstawiona w polu **Nazwa**, a powiązane wiersze rejestracji zostaną wstawione na skróconej karcie **wiersze oceny warunków**.
9. Można wstawiać notatki odnoszące się do wybranej oceny warunku na skróconej karcie **Notatki**.
10. Dla każdego wiersza oceny warunku wstaw dane pomiarowe w polu **Wartość**.
11. Można wstawić komentarz odnoszący się do wybranego wiersza rejestracji na skróconej karcie **wiersze oceny warunków** > **pole komentarzy**. Dodanie komentarza do wiersza powoduje automatyczne zaznaczenie pola wyboru **Komentarz**.

Po dokonaniu rejestracji oceny warunków dla składnika majątku można wydrukować raport oceny stanu.

>[!NOTE]
>Można również zarejestrować oceny stanu w zleceniu pracy (**Zarządzanie składnikiem majątku** > **Wspólne** > **Zlecenia pracy** > **Wszystkie zlecenia pracy** > **Ocena warunku**.)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]