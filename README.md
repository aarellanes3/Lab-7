# Lab-7
def edit_distance(word1, word2):
    num_matrix = [word1][word2]
    for i in range(len(word1)):
        num_matrix = [i][0] * 0
        for j in range(len(word2)):
            num_matrix= [0][j] * 0

            prev = num_matrix[i-1][j]
            diagonal = num_matrix[i][j]
            top = num_matrix[i][j-1]

            if word1[i] == word2[i]:
                num_matrix[i][j] = diagonal

            while word1[i] != word2[i]:
                if prev < diagonal and prev < top:
                    num_matrix[i][j] = prev + 1
                if top < diagonal and top< diagonal:
                    num_matrix[i][j] = top + 1
                if diagonal < prev and diagonal < top:
                    num_matrix[i][j] = diagonal + 1
    return num_matrix
