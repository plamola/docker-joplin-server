#   d o c k e r - j o p l i n - s e r v e r  
  
 [ ! [ D o c k e r   B u i l d   S t a t u s ] ( h t t p s : / / i m g . s h i e l d s . i o / d o c k e r / c l o u d / b u i l d / f l o r i d e r 8 9 / j o p l i n - s e r v e r . s v g ) ] ( h t t p s : / / h u b . d o c k e r . c o m / r / f l o r i d e r 8 9 / s m o k e p i n g - s p e e d t e s t / )   [ ! [ D o c k e r   P u l l s ] ( h t t p s : / / i m g . s h i e l d s . i o / d o c k e r / p u l l s / f l o r i d e r 8 9 / j o p l i n - s e r v e r . s v g ) ] ( h t t p s : / / h u b . d o c k e r . c o m / r / f l o r i d e r 8 9 / s m o k e p i n g - s p e e d t e s t / )   [ ! [ D o c k e r   A u t o m a t e d   b u i l d ] ( h t t p s : / / i m g . s h i e l d s . i o / d o c k e r / c l o u d / a u t o m a t e d / f l o r i d e r 8 9 / j o p l i n - s e r v e r . s v g ) ] ( h t t p s : / / h u b . d o c k e r . c o m / r / f l o r i d e r 8 9 / s m o k e p i n g - s p e e d t e s t / )  
  
 A   D o c k e r   I m a g e   t o   r u n   [ J o p l i n   S e r v e r ] ( h t t p s : / / g i t h u b . c o m / l a u r e n t 2 2 / j o p l i n / t r e e / d e v / p a c k a g e s / s e r v e r ) .  
  
 ! [ J o p l i n   S e r v e r ] ( h t t p s : / / p 1 9 5 . p 4 . n 0 . c d n . g e t c l o u d a p p . c o m / i t e m s / L 1 u O 8 y x 1 / d c 0 1 a 2 8 3 - f 2 f c - 4 5 3 b - a 5 0 4 - 6 1 8 5 7 c a 9 c 6 6 3 . p n g ? v = 8 2 a 8 8 b f 8 a 1 e 9 1 1 9 f 9 f a 2 a 5 1 1 f f e 3 c 5 5 a )  
  
 # #   U s a g e  
  
 T h e   f o l l o w i n g   ` d o c k e r - c o m p o s e . y m l `   w i l l   m a k e   J o p l i n   S e r v e r   a v a i l a b l e   o n   2 2 3 0 0 .   T h e r e   a r e   2   n e t w o r k s   i n   t h e   e x a m p l e   b e l o w ,   o n e   t o   t a l k   t o   t r a e f i k   a n d   o n e   b e t w e e n   t h e   J o p l i n   S e r v e r   a n d   t h e   D a t a b a s e .  
  
 ` ` ` y a m l  
 v e r s i o n :   ' 3 '  
      
 s e r v i c e s :  
         a p p :  
                 e n v i r o n m e n t :  
                         -   J O P L I N _ B A S E _ U R L = h t t p s : / / y o u r . d o m a i n . t l d  
                         -   J O P L I N _ P O R T = 2 2 3 0 0  
                 r e s t a r t :   u n l e s s - s t o p p e d  
                 i m a g e :   f l o r i d e r 8 9 / j o p l i n - s e r v e r : l a t e s t  
                 # b u i l d :  
                 #         c o n t e x t :   .  
                 #         d o c k e r f i l e :   D o c k e r f i l e . s e r v e r  
                 # p o r t s :  
                 #         -   " $ { J O P L I N _ P O R T } : $ { J O P L I N _ P O R T } "  
                 #   v o l u m e s :  
                 #           #   M o u n t   t h e   s e r v e r   d i r e c t o r y   s o   t h a t   i t ' s   p o s s i b l e   t o   e d i t   f i l e  
                 #           #   w h i l e   t h e   c o n t a i n e r   i s   r u n n i n g .   H o w e v e r   d o n ' t   m o u n t   t h e  
                 #           #   n o d e _ m o d u l e s   d i r e c t o r y   w h i c h   w i l l   b e   s p e c i f i c   t o   t h e   D o c k e r  
                 #           #   i m a g e   ( e g   n a t i v e   m o d u l e s   w i l l   b e   b u i l t   f o r   U b u n t u ,   w h i l e   t h e  
                 #           #   c o n t a i n e r   m i g h t   b e   r u n n i n g   i n   W i n d o w s )  
                 #           #   h t t p s : / / s t a c k o v e r f l o w . c o m / a / 3 7 8 9 8 5 9 1 / 5 6 1 3 0 9  
                 #           -   . / p a c k a g e s / s e r v e r : / h o m e / j o p l i n / p a c k a g e s / s e r v e r  
                 #           -   / h o m e / j o p l i n / p a c k a g e s / s e r v e r / n o d e _ m o d u l e s /  
                 n e t w o r k s :  
                         -   i n t e r n a l  
                         -   t r a e f i k _ d e f a u l t  
  
         d b :  
                 r e s t a r t :   u n l e s s - s t o p p e d  
                 #   B y   d e f a u l t ,   t h e   P o s t g r e s   i m a g e   s a v e s   t h e   d a t a   t o   a   D o c k e r   v o l u m e ,  
                 #   s o   i t   p e r s i s t s   w h e n e v e r   t h e   s e r v e r   i s   r e s t a r t e d   u s i n g  
                 #   ` d o c k e r - c o m p o s e   u p ` .   N o t e   t h a t   i t   w o u l d   h o w e v e r   b e   d e l e t e d   w h e n  
                 #   r u n n i n g   ` d o c k e r - c o m p o s e   d o w n ` .  
                 # b u i l d :  
                 #         c o n t e x t :   .  
                 #         d o c k e r f i l e :   D o c k e r f i l e . d b  
                 i m a g e :   p o s t g r e s : 1 3 . 1  
                 # p o r t s :  
                 #         -   " 5 4 3 2 : 5 4 3 2 "  
                 n e t w o r k s :  
                         -   i n t e r n a l  
                 v o l u m e s :  
                         -   / h o m e / f l o r i a n / d o c k e r / j o p l i n - d a t a : / v a r / l i b / p o s t g r e s q l / d a t a  
                 e n v i r o n m e n t :  
                         #   T O D O :   C o n s i d e r i n g   t h e   d a t a b a s e   i s   o n l y   e x p o s e d   t o   t h e  
                         #   a p p l i c a t i o n ,   a n d   n o t   t o   t h e   o u t s i d e   w o r l d ,   i s   t h e r e   a   n e e d   t o  
                         #   p i c k   a   s e c u r e   p a s s w o r d ?  
                         -   P O S T G R E S _ P A S S W O R D = j o p l i n  
                         -   P O S T G R E S _ U S E R = j o p l i n  
                         -   P O S T G R E S _ D B = j o p l i n  
 n e t w o r k s :  
     i n t e r n a l :  
         i n t e r n a l :   t r u e  
     t r a e f i k _ d e f a u l t :  
         e x t e r n a l :   t r u e  
 ` ` `  
  
  
  
 # #   T a g s  
  
 C u r r e n t l y   t h e r e   i s   o n l y   o n e   v e r s i o n   a s   t h e r e   i s   n o   r e l e a s e   y e t   f o r   t h e   s e r v e r .  
  
 ` l a t e s t ` :   r e g u l a r   b u i l d s   o f   t h e   ` d e v `   b r a n c h .   T h i s   w i l l   c h a n g e   t o   t h e   l a t e s t   r e l e a s e   o n c e   a v a i l a b l e .  
  
  
  
 # #   C o n t r i b u t e  
  
 F e e l   f r e e   t o   c o n t r i b u t e   t o   t h i s   D o c k e r   i m a g e   o n   [ G i t h u b ] ( h t t p s : / / g i t h u b . c o m / f l o s o f t / d o c k e r - j o p l i n - s e r v e r ) . 