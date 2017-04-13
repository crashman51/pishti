# pishti
import java.util.ArrayList;
//ELIZABETH BURNSIDE

public class deck {

    ArrayList<Card> drawPile = new ArrayList<>();
    ArrayList<Card> discardPile = new ArrayList<>();

    public deck(){

        for(int i = 1; i < 53; i++)
            {
                Card draw = new Card(i);
                drawPile.add(draw);
            }
        java.util.Collections.shuffle(drawPile);
    }


    public void draw(player currentPlayer){
        player lastPlayer = currentPlayer;
        if(drawPile.size() < 2)
        {

            lastPlayer.addToHand(drawPile.get(0));
            updateDrawPile(drawPile.get(0));
        }

        else{
            lastPlayer.addToHand(drawPile.get(0));
            lastPlayer.addToHand(drawPile.get(0));
            endGame();
        }

    }


    public void updateDrawPile(Card currentCard){drawPile.remove(currentCard);}


    public void discard(player currentPlayer, Card currentCard){discardPile.add(0, currentCard);}

    public void endGame(){};
}
